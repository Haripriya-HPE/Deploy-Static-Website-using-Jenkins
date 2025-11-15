# Deploy a Static Website on AWS EC2 using Jenkins
This project demonstrates a complete CI/CD pipeline where Jenkins automatically deploys a static website to an AWS EC2 web server.

# Technologies Used
1. AWS EC2 (Ubuntu) – Jenkins server + Web server
2. Jenkins – CI/CD automation
3. Nginx – Web server for hosting static site
4. GitHub – Source code repository
5. Shell script (deploy.sh) – Deployment automation

# CI/CD Pipeline Flow
1) Developer updates code on GitHub - Any modification triggers the pipeline.

2) Jenkins pulls code - Jenkins uses Git plugin to fetch latest commit.

3) Deployment Stage - Jenkins executes deploy.sh -> Script copies static files to the Web Server -> Nginx automatically serves updated files

4) Website is Live - Users can access via server public IP.

# Setup Web Server
1. Install Nginx
2. Start and Enable Nginx
3. Create Website Directory

# Setup Jenkins Server
1. Install Java
2. Install Jenkins
3. Start Jenkins

# Jenkins Freestyle Job Setup
1) Create Freestyle Project

2) Source Code Management -> Git -> Add GitHub repo URL

3) Build Steps → Execute Shell

4) Save & Build Now

# Access the Website
Open browser -> Search "Web Server Public IP"
Website is live
