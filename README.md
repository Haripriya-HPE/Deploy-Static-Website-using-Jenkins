# Deploy a Static Website on AWS EC2 using Jenkins
This project demonstrates a complete CI/CD pipeline where Jenkins automatically deploys a static website to an AWS EC2 web server.

# Technologies Used
AWS EC2 (Ubuntu) – Jenkins server + Web server
Jenkins – CI/CD automation
Nginx – Web server for hosting static site
GitHub – Source code repository
Shell script (deploy.sh) – Deployment automation
SSH / SCP – Remote file transfer

# CI/CD Pipeline Flow
1) Developer updates code on GitHub

Any modification triggers the pipeline.

2) Jenkins pulls code

Jenkins uses Git plugin to fetch latest commit.

3) Deployment Stage

Jenkins executes deploy.sh

Script copies static files to the Web Server

Nginx automatically serves updated files

4) Website is Live

Users can access via EC2 public IP.

# Web Server Setup
1. Update and install Nginx
sudo apt update
sudo apt install nginx -y

2. Start & enable
sudo systemctl start nginx
sudo systemctl enable nginx

3. Website directory
sudo rm -rf /var/www/html/*

# Jenkins Server Setup
1. Install Java
sudo apt update
sudo apt install openjdk-17-jdk -y

2. Install Jenkins
curl -fsSL https://pkg.jenkins.io/debian/jenkins.io.key | sudo tee \
  /usr/share/keyrings/jenkins-keyring.asc > /dev/null

echo deb [signed-by=/usr/share/keyrings/jenkins-keyring.asc] \
  https://pkg.jenkins.io/debian binary/ | sudo tee \
  /etc/apt/sources.list.d/jenkins.list > /dev/null

sudo apt update
sudo apt install jenkins -y

3. Start Jenkins
sudo systemctl enable jenkins
sudo systemctl start jenkins

# Jenkins Freestyle Job Setup
1) Create Freestyle Project

2) Source Code Management -> Git -> Add GitHub repo URL

3) Build Steps → Execute Shell
Add:
bash scripts/deploy.sh

4)Save & Build Now

# Access the Website
Open browser -> Search "Web Server Public IP"
