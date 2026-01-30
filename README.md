# Brain Tasks App – Docker & Kubernetes Deployment on AWS EKS

This project demonstrates the deployment of a containerized frontend application on AWS using Docker, Amazon ECR, and Amazon EKS.  
The focus of this project is on containerization, Kubernetes deployment, and AWS infrastructure usage.

---

## 🚀 Project Overview

- React frontend application
- Application built and served as static files
- Docker image created and pushed to Amazon ECR
- Kubernetes Deployment and Service created on Amazon EKS
- Application exposed using Kubernetes LoadBalancer service

---

## 🛠️ Technology Stack

| Category | Tools / Services |
|-------|----------------|
| Frontend | React |
| Containerization | Docker |
| Container Registry | Amazon ECR |
| Orchestration | Kubernetes |
| Managed Kubernetes | Amazon EKS |
| Cloud Platform | AWS |
| Version Control | GitHub |

---

## 🏗️ Architecture Overview

### High-Level Flow

User  
⬇  
AWS Load Balancer (via Kubernetes Service)  
⬇  
Amazon EKS Cluster  
⬇  
Kubernetes Pods (NGINX serving React build)  
⬇  
Docker Image from Amazon ECR  

---

### Architecture Components

| Component | Purpose |
|--------|--------|
| GitHub | Source code repository |
| Docker | Containerization of application |
| Amazon ECR | Stores Docker images |
| Amazon EKS | Manages Kubernetes control plane |
| EC2 Node Group | Runs application pods |
| Kubernetes Service | Exposes application externally |

---

## 📦 Docker Implementation

- Application build output (`dist/`) served using **NGINX**
- Lightweight NGINX Alpine base image
- Production-ready container

### Docker Workflow

1. Clone GitHub repository
2. Build Docker image
3. Push image to Amazon ECR
4. Image pulled by Kubernetes during deployment

---

## ☸️ Kubernetes Deployment

Kubernetes configuration includes:

### Deployment
- Defines application pods
- Uses Docker image from Amazon ECR
- Ensures application availability

### Service
- Type: `LoadBalancer`
- Exposes application to the internet
- Automatically provisions AWS Load Balancer

---

## 🔐 AWS & Security Setup

- AWS IAM role attached to EC2 instance
- Secure access to Amazon ECR
- No hardcoded credentials
- Network access controlled via Security Groups

---

## 🧪 Errors Faced & Fixes

During the implementation, the following issues were encountered and resolved:

- Docker build failure due to missing build directory
- Incorrect Docker build context
- EKS nodegroup creation failure due to VPC CNI issues
- Kubernetes context misconfiguration
- GitHub permission and authentication issues

Each issue was resolved through troubleshooting AWS and Kubernetes configurations.

---
