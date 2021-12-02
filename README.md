# Greetings, coder
You've stumbled upon illustrated instructions for deploying your full-stack app using a monorepo with a front-end subdirectory and a back-end subdirectory. 

# Instructions
Pre-requisites:
  - [ ] You have GitHub, Heroku and Vercel accounts.
  - [ ] Your monorepo is on GitHub.
  - [ ] Your code works.

## 0. Back-end: Heroku
### 0.0 Create a new Heroku app
![Screen Shot 2021-12-01 at 7 15 37 PM](https://user-images.githubusercontent.com/86169488/144518106-5139e65f-88de-4398-aa71-602d382326c6.png)

### 0.1 Navigate to "Settings"
![Screen Shot 2021-12-01 at 7 47 59 PM](https://user-images.githubusercontent.com/86169488/144518177-8f8a8043-1a2b-46e7-a955-fd5067ba3af3.png)

### 0.1.0 Config Vars (equivalent to .env vars in Node.js)
Click "Reveal Config Vars" and add the following variables:

  Subdirectory variable: used by the buildack to find the subdirectory.
  - [ ] key: APP_BASE
  - [ ] value: name of back-end subdirectory.

  Database url variable: used by your app to connect to its database. Its key MUST match the environment variable referenced in your code's database configuration (e.g. knexfile.js).
  - [ ] key: YOUR_DATABASE_VARIABLE 
  - [ ] value: your database url.

#### 0.1.1 Buildpacks
Click "Add buildpack" and enter the following URL:
 - [ ] https://github.com/lstoll/heroku-buildpack-monorepo (always do this one first)

One more time:
 - [ ] heroku/nodejs

### 0.2 Navigate to "Deploy"
![Screen Shot 2021-12-01 at 7 16 43 PM](https://user-images.githubusercontent.com/86169488/144517262-faa3d838-2d7a-4389-943e-b4048bc51c96.png)

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
![Screen Shot 2021-12-02 at 12 08 32 AM copy](https://user-images.githubusercontent.com/86169488/144517333-ca700ea4-ea3a-4385-9b61-9d3f5a211252.png)

#### 1.0.0 Import Git Repository
Click the "Select a Git Namespace" field, then click "Add GitHub Namespace". This will open the Vercel installer on GitHub.

### 1.1 Install Vercel
![Screen Shot 2021-12-01 at 10 54 27 PM](https://user-images.githubusercontent.com/86169488/144517705-fb95178b-8e37-4733-9a03-3c2f1abda9fe.png)

Click on the desired GitHub account.

Choose your installation scope: "All repositories" or "Only select repositories".

Click "Install" to return to Vercel.

### 1.2 Import Repository
![Screen Shot 2021-12-02 at 12 08 32 AM](https://user-images.githubusercontent.com/86169488/144517935-2635bab6-875a-4fde-a114-f54a4371f84f.png)

Click "Import" on the desired repo.

### 1.3 Configure Project
![Screen Shot 2021-12-02 at 4 46 36 PM](https://user-images.githubusercontent.com/86169488/144517948-25d5f155-cb8a-448e-9402-c89d1e60e3b1.png)

#### 1.3.0 Framework Preset
Select "Create React App'.
#### 1.3.1 Root Directory
Click "Edit", then click on your front-end subdirectory, then click "Continue".
#### 1.3.2 Deploy
Click "Deploy".

 ## 2. Done
Your app is deployed and every time you push changes to the GitHub monorepo's main branch, it will redeploy — no subtree pushing required.
![Screen Shot 2021-12-02 at 4 32 00 PM](https://user-images.githubusercontent.com/86169488/144518335-20cfc9cf-cb16-46ca-bb38-c0a7f2f1d364.png)

