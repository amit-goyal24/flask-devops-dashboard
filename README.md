# 🚀 Flask DevOps Dashboard – CI/CD on AWS

Welcome to the Flask DevOps Dashboard! This project demonstrates how to build and deploy a simple Python Flask application using a full CI/CD pipeline powered by **AWS CodePipeline**, **CodeBuild**, and **EC2** — with **CloudWatch** monitoring.

---

## 📦 Features

- 🌐 Simple Flask app with a single route (`/`)
- 🛠️ CI/CD using AWS CodePipeline + CodeBuild
- 🐳 Dockerized application
- 🖥️ Deployment to EC2 (Free Tier)
- 📊 Monitoring using AWS CloudWatch

---

## 📁 Project Structure

flask-devops-dashboard/
├── app.py # Main Flask app
├── requirements.txt # Python dependencies
├── Dockerfile # For containerizing the app
├── buildspec.yml # AWS CodeBuild instructions
└── README.md # You're reading it right now

yaml
Copy
Edit

---

## ⚙️ Prerequisites

Before deploying, make sure you have:

- ✅ AWS Account (Free Tier works)
- ✅ IAM roles with access to CodePipeline, CodeBuild, EC2
- ✅ GitHub repository with this project
- ✅ EC2 instance with Docker installed
- ✅ Security group allowing ports 22 (SSH) and 5000 (Flask)

---

## 🚧 Step-by-Step Guide

### 🧱 1. Clone this Repo

git clone https://github.com/<your-username>/flask-devops-dashboard.git
cd flask-devops-dashboard
🐳 2. Run Locally with Docker (Optional)
bash
Copy
Edit
docker build -t flask-dashboard .
docker run -d -p 5000:5000 flask-dashboard
Visit: http://localhost:5000

☁️ 3. Setup AWS EC2 Instance
Launch a t2.micro EC2 (Amazon Linux 2)

Install Docker:

bash
Copy
Edit
sudo yum update -y
sudo yum install docker -y
sudo service docker start
sudo usermod -aG docker ec2-user
Re-login after modifying groups.

🚀 4. Create CodePipeline
Go to AWS CodePipeline

Create new pipeline

Source: GitHub (connect your repo)

Build: CodeBuild (point to buildspec.yml)

Deploy: Manual (or later with CodeDeploy)
