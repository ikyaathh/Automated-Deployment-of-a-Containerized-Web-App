# Automated-Deployment-of-a-Containerized-Web-App

This is a beginner-friendly DevOps project demo the complete workflow from code to deployment using Docker and GitHub.

##  Project Overview

The goal of this project is to:

- Create a simple web app
- Containerize it using Docker
- Deploy it on an AWS EC2 instance
- Track code changes using Git & GitHub

This demonstrates the core DevOps concepts: automation, containerization, version control, and deployment.

---

##  Tools & Technologies Used

- Linux (Ubuntu) – Server environment  
- Docker – Containerization  
- AWS EC2 – Cloud server deployment  
- Git & GitHub – Version control  
- HTML – Simple web app  

STEPS I FOLLOWED:

-## Step 1: Setup Ec2 Server

- Launched an Ubuntu EC2 instance on AWS
- Connected to the server via SSH from my personal computer
- Updated packages:
Bash (code)
sudo apt update
sudo apt upgrade -y

-## Installed Docker on EC2

Bash (code)
sudo apt install docker.io -y
sudo systemctl start docker
sudo systemctl enable docker
sudo usermod -aG docker $USER

-## Created Simple Web App

-Created index.html with a simple "Hello from DevOps" message
-Created Dockerfile to containerize the app:

Bash (code)
FROM nginx:latest
COPY index.html /usr/share/nginx/html/index.html

-## Built and Ran Docker Container

Bash (code)
docker build -t devops-app .
docker run -d -p 80:80 devops-app

-Verified container was running: docker ps
-Configured EC2 security group to allow HTTP (port 80)
-Checked web app in browser: http://<EC2_PUBLIC_IP>

-## Version Control with Git

-Initialized Git in project folder:

Bash (code)
git init
git add .
git commit -m "Initial commit - Dockerized EC2 app"


-Connected to GitHub repository:

Bash (code)
git remote add origin https://github.com/ikyaathh/Automated-Deployment-of-a-Containerized-Web-App.git
git branch -M main
git push origin main

-#Resolved merge conflicts from pre-existing README and LICENSE
