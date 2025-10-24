# GitHub Repository Setup Guide

Since you downloaded the ZIP file, you need to create your own GitHub repository and push the code.

## 🚀 Step-by-Step Instructions

### **Step 1: Create GitHub Repository**

1. Go to https://github.com/new
2. Fill in the details:
   - **Repository name**: `xrwvm-fullstack-capstone` (or any name you prefer)
   - **Description**: "Full-stack car dealership application - Coursera Capstone Project"
   - **Visibility**: ✅ **Public** (required for submission)
   - **DO NOT** check "Add a README file"
   - **DO NOT** add .gitignore or license
3. Click **"Create repository"**
4. **Copy the repository URL** (it will look like: `https://github.com/YOUR_USERNAME/xrwvm-fullstack-capstone.git`)

---

### **Step 2: Initialize Git and Push Code**

Open PowerShell and run these commands **one by one**:

```powershell
# Navigate to your project folder
cd "d:\NOTES\coursera6\xrwvm-fullstack_developer_capstone-main"

# Initialize Git repository
git init

# Add all files
git add .

# Create first commit
git commit -m "Initial commit - Full-stack car dealership capstone project"

# Rename branch to main
git branch -M main

# Add your GitHub repository as remote (REPLACE WITH YOUR URL)
git remote add origin https://github.com/YOUR_USERNAME/YOUR_REPO_NAME.git

# Push to GitHub
git push -u origin main
```

**IMPORTANT**: Replace `https://github.com/YOUR_USERNAME/YOUR_REPO_NAME.git` with the actual URL you copied in Step 1.

---

### **Step 3: Verify Upload**

1. Go to your GitHub repository in the browser
2. You should see all your files including:
   - `server/` folder
   - `screenshots/` folder
   - `README.md`
   - `.github/` folder (with CI/CD workflows)

---

### **Step 4: Submit the URL**

Copy your repository URL (without the `.git` at the end) and submit it for **Task 1**.

Example: `https://github.com/YOUR_USERNAME/xrwvm-fullstack-capstone`

---

## ⚠️ Troubleshooting

### If you get "git is not recognized"
You need to install Git for Windows:
1. Download from: https://git-scm.com/download/win
2. Install with default settings
3. Restart PowerShell
4. Try the commands again

### If you get authentication errors
GitHub may require a Personal Access Token instead of password:
1. Go to: https://github.com/settings/tokens
2. Click "Generate new token (classic)"
3. Give it a name like "Coursera Project"
4. Check the "repo" scope
5. Generate and copy the token
6. Use this token as your password when pushing

---

## ✅ Once Complete

You'll have:
- ✅ Your code on GitHub (Task 1)
- ✅ A public repository URL to submit
- ✅ All 26 screenshots ready to upload
- ⚠️ Still need: Deployment URL (Task 24)

---

**Need help?** Let me know if you encounter any errors!
