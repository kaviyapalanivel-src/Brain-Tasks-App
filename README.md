🧠 Brain Tasks App
Docker, Kubernetes & CI Pipeline Deployment on AWS

This project demonstrates a production-style DevOps workflow for deploying a frontend application using Docker, Kubernetes, and AWS Cloud services.
It also includes a Continuous Integration (CI) pipeline using AWS CodePipeline.

📌 Project Objective

The goal of this project is to showcase:

Containerization of a frontend application

Kubernetes deployment on AWS

Image management using Amazon ECR

Automated build validation using AWS CodePipeline

Real-world DevOps practices

🗂️ Project Features

✨ Frontend application containerized with Docker
📦 Docker images stored securely in Amazon ECR
☸️ Application deployed on Amazon EKS
🌐 Public access via Kubernetes LoadBalancer
🔁 CI pipeline triggered on GitHub code push

🛠️ Technology Stack
Layer	Tool / Service
Frontend	React
Containerization	Docker
Container Registry	Amazon ECR
Orchestration	Kubernetes
Managed Kubernetes	Amazon EKS
CI/CD	AWS CodePipeline, AWS CodeBuild
Cloud Provider	AWS
Version Control	GitHub
🏗️ High-Level Architecture
Developer
   |
   v
GitHub Repository
   |
   v
AWS CodePipeline (CI)
   |
   v
Docker Image Build
   |
   v
Amazon ECR
   |
   v
Amazon EKS Cluster
   |
   v
Kubernetes Pods (NGINX + React)
   |
   v
AWS Load Balancer
   |
   v
End Users

📁 Repository Structure
File / Folder	Description
Dockerfile	Docker image definition
buildspec.yml	CI build instructions
deployment.yaml	Kubernetes Deployment manifest
service.yaml	Kubernetes Service manifest
dist/	React production build
screenshots/	Output and verification screenshots
README.md	Project documentation
🐳 Docker Implementation

Uses NGINX Alpine as a lightweight base image

Serves React build files from dist/

Optimized for production usage

Docker Workflow

Clone the GitHub repository

Build Docker image locally / via CI

Push Docker image to Amazon ECR

Kubernetes pulls image from ECR during deployment

☸️ Kubernetes Deployment (EKS)
Deployment Configuration

Defines desired number of pods

Uses Docker image from Amazon ECR

Ensures high availability

Service Configuration

Type: LoadBalancer

Exposes application to the internet

Automatically provisions AWS Load Balancer

🔐 AWS & Security Configuration

IAM role attached to EC2 worker nodes

Secure ECR access without hardcoded credentials

Network access controlled using Security Groups

Kubernetes resources isolated within VPC

🔄 Continuous Integration with AWS CodePipeline

This project includes a CI pipeline to automatically validate builds when code is pushed to GitHub.

CI Tools Used
Purpose	Service
Source	GitHub
Pipeline Orchestration	AWS CodePipeline
Build Execution	AWS CodeBuild
Build Instructions	buildspec.yml
CI Pipeline Stages

Source Stage

GitHub connected via GitHub App

Monitors main branch

Triggers automatically on every push

Build Stage

Runs on AWS CodeBuild

Installs dependencies

Executes application build

Logs stored in CloudWatch

buildspec.yml (CI Build File)
version: 0.2
phases:
  install:
    runtime-versions:
      nodejs: 18
    commands:
      - npm install
  build:
    commands:
      - npm run build

🧪 Issues Faced & Resolutions
Issue	Resolution
Docker build failed	Corrected build context and paths
Missing build files	Generated React production build
GitHub push permission error	Used correct fork & authentication
CodePipeline build failure	Fixed Node.js version and commands
Kubernetes access issue	Updated kubeconfig and context
✅ Final Outcome

✔️ Application successfully deployed on AWS EKS
✔️ Docker image managed via Amazon ECR
✔️ CI pipeline validates every code change
✔️ End-to-end DevOps workflow implemented

📎 Conclusion

This project demonstrates a real-time DevOps implementation using modern cloud-native tools.
It highlights best practices in containerization, Kubernetes orchestration, and CI automation on AWS.
