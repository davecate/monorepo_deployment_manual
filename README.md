# Greetings, coder
You've stumbled upon illustrated instructions for deploying your full-stack app using a monorepo with a front-end subdirectory and a back-end subdirectory. 

# Instructions
Pre-requisites:
  — [ ] You have GitHub, Heroku and Vercel accounts.
  — [ ] Your monorepo is on GitHub.
  — [ ] Your code works.

## 0. Back-end: Heroku
### 0.0 Create a new Heroku app

### 0.1 Navigate to "Settings"
#### 0.1.0 Config Vars (equivalent to .env vars in Node.js)
Click "Reveal Config Vars" and add the following variables:
  Subdirectory variable: used by the buildack to find the subdirectory.
  — [ ] key: APP_BASE value: name of back-end subdirectory.

  Database url variable: used by your app to connect to its database. Its key MUST match the environment variable referenced in your code's database configuration (e.g. knexfile.js).
  — [ ] key: YOUR_DATABASE_VARIABLE value: your database url.

#### 0.1.1 Buildpacks
Click "Add buildpack" and enter the following URL:
 — [ ] https://github.com/lstoll/heroku-buildpack-monorepo (always do this one first)
One more time:
 — [ ] heroku/nodejs

### 0.2 Navigate to "Deploy"
#### 0.2.0 Deployment method
Select Github
#### 0.2.1 Apps connected to GitHub
Search for your app on GitHub and hit "Connect" on the desired result
#### 0.2.2 Automatic deploys
Enable automatic deploys. Now your app re-deploys every time you push to GitHub.
#### 0.2.3 Manual Deploy
If you can't wait for your next push to GitHub, click "Deploy Branch" to deploy your code.

## 1. Front-end: Vercel
### 1.0 Create a new Vercel project
#### 1.0.1 Import Git Repository
Click the "Select a Git Namespace" field, then click "Add GitHub Namespace". This will open the Vercel installer on GitHub.

### 1.1 Install Vercel
Click on the desired GitHub account.

Choose your installation scope: "All repositories" or "Only select repositories".

Click "Install" to return to Vercel.

### 1.2 Import Repository
Click "Import" on the desired repo.

### 1.3 Configure Project
#### 1.3.0 Root Directory
Click "Edit", then click on your front-end subdirectory, then click "Continue".
#### 1.3.1 Deploy
Click "Deploy".

 ## 2. Done
Your app is deployed and every time you change the GitHub monorepo's main branch, it will redeploy.
