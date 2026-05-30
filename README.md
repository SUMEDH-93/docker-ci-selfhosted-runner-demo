🚀 Docker CI Setup Using GitHub Self-Hosted Runner

🎯 Objective

Configure a GitHub Self-Hosted Runner on an AWS EC2 Ubuntu instance and create a Docker Continuous Integration (CI) pipeline using GitHub Actions and Docker Hub.

🔥 Workflow Overview

✅ Trigger automatically on code push
✅ Run on a Self-Hosted Runner
✅ Build a Docker image
✅ Authenticate with Docker Hub
✅ Push the image to Docker Hub

📋 Prerequisites
🐙 GitHub Account
🐳 Docker Hub Account
☁️ AWS Account
💻 EC2 Ubuntu Instance
🔧 Git Installed
🐳 Docker Installed
📁 GitHub Repository
🏗️ Step 1: Create GitHub Repository

Create a new GitHub repository.

docker-ci-selfhosted-runner-demo

Clone the repository:

git clone https://github.com/<github-username>/docker-ci-selfhosted-runner-demo.git

cd docker-ci-selfhosted-runner-demo
🐳 Step 2: Create Dockerfile

Create a file named:

Dockerfile
☁️ Step 3: Launch AWS EC2 Instance
Recommended Configuration
🖥️ AMI: Ubuntu Server
⚡ Instance Type: t2.micro
💾 Storage: 8 GB
🔒 Security Group
SSH (22)
⚙️ Step 4: Install Docker
Update Packages
sudo apt update
Install Docker
sudo apt install docker.io -y
Verify Installation
docker --version

✅ Docker Installed Successfully

🤖 Step 5: Configure GitHub Self-Hosted Runner

Navigate to:

Repository
→ Settings
→ Actions
→ Runners
→ New Self-Hosted Runner

Select:

Linux
x64

🚀 Start the runner:

./run.sh

Expected Output:

Listening for Jobs

✅ Runner Ready

🔑 Step 6: Create Docker Hub Access Token

Navigate to:

Account Settings
→ Personal Access Tokens

Copy:

👤 Docker Hub Username
🔐 Docker Hub Access Token
🔒 Step 7: Configure GitHub Secrets

Create the following repository secrets:

Secret Name	Purpose
🔑 DOCKERHUB_USERNAME	Docker Hub Username
🔐 DOCKERHUB_TOKEN	Docker Hub Access Token
⚡ Step 8: Create GitHub Actions Workflow

Create:

.github/workflows/main.yml

✅ Workflow Features:

Checkout Code
Set up QEMU
Set up Docker Buildx
Login to Docker Hub
Build Docker Image
Push Docker Image
🚀 Step 9: Trigger Workflow

Push any change:

git add .

git commit -m "Update project"

git push origin main

Navigate to:

Repository
→ Actions

Expected Workflow Stages:

✅ Set up job
✅ Set up QEMU
✅ Set up Docker Buildx
✅ Login to Docker Hub
✅ Build and Push Docker Image
✅ Verification
🤖 Verify Runner Status

Expected:

Runner Status: Idle
⚡ Verify Workflow

Expected:

Workflow Status: Success
🐳 Verify Docker Hub Repository

Expected Image:

your-dockerhub-username/docker-ci-selfhosted-runner-demo

Tag:

latest
🎉 Conclusion

Successfully configured a GitHub Self-Hosted Runner on an AWS EC2 Ubuntu Instance and implemented a Docker CI Pipeline using GitHub Actions and Docker Hub.

🚀 Achievements

✅ Self-Hosted Runner Configured
✅ Docker Installed and Verified
✅ GitHub Secrets Configured
✅ CI Workflow Created
✅ Docker Image Built Automatically
✅ Docker Image Pushed to Docker Hub

Result: Every code push automatically triggers the CI pipeline and publishes the latest Docker image to Docker Hub. 🎯🔥

Mujhe lagta hai README ke top me ek architecture flow bhi add kar dena chahiye:

Developer Push
      │
      ▼
 GitHub Repository
      │
      ▼
 GitHub Actions
      │
      ▼
 Self-Hosted Runner (EC2)
      │
      ▼
 Docker Build
      │
      ▼
 Docker Hub
