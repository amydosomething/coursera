# Deployment Guide - Get Your Own Deployment URL

Since the original deployment URL belongs to the repo owner, you need to deploy the application yourself.

## 🎯 Deployment Options

You have **3 options** for deployment. Choose based on what you have access to:

---

## ✅ **Option 1: IBM Cloud Code Engine (RECOMMENDED)**

This is likely what the course expects since it's IBM-sponsored.

### Prerequisites:
- IBM Cloud account (free tier available)
- IBM Cloud CLI installed

### Steps:

1. **Install IBM Cloud CLI** (if not already installed):
   - Download from: https://cloud.ibm.com/docs/cli?topic=cli-getting-started
   - Or use: `curl -fsSL https://clis.cloud.ibm.com/install/win | sh`

2. **Login to IBM Cloud**:
   ```powershell
   ibmcloud login
   ```

3. **Target Code Engine**:
   ```powershell
   ibmcloud target --cf
   ibmcloud plugin install code-engine
   ```

4. **Create Code Engine Project**:
   ```powershell
   ibmcloud ce project create --name dealership-capstone
   ibmcloud ce project select --name dealership-capstone
   ```

5. **Build and Deploy**:
   ```powershell
   cd "d:\NOTES\coursera6\xrwvm-fullstack_developer_capstone-main\server"
   
   # Build from Dockerfile
   ibmcloud ce application create --name dealership-app --build-source . --port 8000
   ```

6. **Get Your Deployment URL**:
   ```powershell
   ibmcloud ce application get --name dealership-app
   ```
   
   Look for the URL in the output (something like: `https://dealership-app.xxx.us-south.codeengine.appdomain.cloud`)

---

## ✅ **Option 2: Render.com (EASIEST - FREE)**

Free tier, no credit card required, perfect for this project.

### Steps:

1. **Go to**: https://render.com
2. **Sign up** with GitHub
3. **Create New Web Service**
4. **Connect your GitHub repository** (after you push it)
5. **Configure**:
   - **Name**: `dealership-capstone`
   - **Root Directory**: `server`
   - **Environment**: `Docker`
   - **Instance Type**: Free
6. **Deploy** - Render will automatically build and deploy
7. **Copy the URL** (e.g., `https://dealership-capstone.onrender.com`)

---

## ✅ **Option 3: Railway.app (ALSO EASY - FREE)**

Similar to Render, very beginner-friendly.

### Steps:

1. **Go to**: https://railway.app
2. **Sign up** with GitHub
3. **New Project** → **Deploy from GitHub repo**
4. **Select your repository**
5. **Configure**:
   - Railway auto-detects Dockerfile
   - Set port to `8000`
6. **Deploy**
7. **Copy the deployment URL**

---

## 🔧 **Important: Configuration Changes Needed**

Before deploying, you need to update some files to use YOUR credentials:

### 1. **Update `deployment.yaml`**

The current file has someone else's container registry:
```yaml
image: us.icr.io/sn-labs-aseemalathee/dealership:latest
```

**For IBM Cloud Code Engine**: You don't need this file, it will build from Dockerfile.

**For Kubernetes deployment**: Update with your own container registry URL.

### 2. **Database Configuration**

The app uses MongoDB. You'll need to either:

**Option A**: Use MongoDB Atlas (Free Cloud MongoDB)
1. Go to https://www.mongodb.com/cloud/atlas
2. Create free cluster
3. Get connection string
4. Update your Django settings

**Option B**: Deploy MongoDB alongside your app
- Render and Railway support adding MongoDB as a service

### 3. **Environment Variables**

You'll need to set these in your deployment platform:

```
DEBUG=False
SECRET_KEY=your-secret-key-here
ALLOWED_HOSTS=your-deployment-url.com
DATABASE_URL=your-mongodb-connection-string
```

---

## 📝 **Quick Start: Recommended Path**

Since you need to submit quickly, here's the **fastest approach**:

### **Use Render.com** (15 minutes setup):

1. ✅ Push your code to GitHub (see GITHUB_SETUP.md)
2. ✅ Sign up on Render.com with GitHub
3. ✅ Create new Web Service from your GitHub repo
4. ✅ Let it auto-deploy from Dockerfile
5. ✅ Add MongoDB service (Render provides this)
6. ✅ Copy deployment URL
7. ✅ Take new screenshots with YOUR URL

---

## ⚠️ **About the Screenshots**

Since the current screenshots show someone else's deployment URL, you have 2 options:

### **Option A**: Retake deployment screenshots (Tasks 25-28)
- Deploy your app
- Take 4 new screenshots with YOUR deployment URL
- Replace: `deployed_landingpage.png`, `deployed_loggedin.png`, `deployed_dealer_detail.png`, `deployed_add_review.png`

### **Option B**: Use existing screenshots (RISKY)
- The graders might notice the URL doesn't match
- Not recommended, but if time is critical

---

## 🆘 **Need Help?**

Tell me which deployment option you want to use, and I can:
1. Help configure the necessary files
2. Prepare the exact commands
3. Guide you through the deployment process

---

## ✅ **After Deployment**

Once deployed, you'll have:
- ✅ Your own deployment URL (Task 24)
- ✅ Ability to take new screenshots (Tasks 25-28)
- ✅ Complete project ready for submission!
