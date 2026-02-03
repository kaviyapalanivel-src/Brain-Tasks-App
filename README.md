
# 🧠 Brain Tasks App  
## Docker, Kubernetes & CI Pipeline Deployment on AWS

This project demonstrates a **production-style DevOps workflow** for deploying a frontend application using **Docker**, **Kubernetes**, and **AWS Cloud services**.  
It also includes a **Continuous Integration (CI) pipeline** implemented using **AWS CodePipeline**.

---

## 🎯 Project Objective

The primary objective of this project is to demonstrate:

- Containerization of a frontend application
- Kubernetes-based deployment on AWS
- Docker image management using Amazon ECR
- Automated build validation using CI pipeline
- Practical DevOps best practices

---

## ✨ Key Features

- Frontend application containerized using Docker  
- Secure image storage with Amazon ECR  
- Application deployment on Amazon EKS  
- Public access enabled via Kubernetes LoadBalancer  
- CI pipeline triggered automatically on GitHub commits  

---

## 🧰 Technology Stack

| Category | Tools / Services |
|--------|------------------|
| Frontend | React |
| Containerization | Docker |
| Container Registry | Amazon ECR |
| Orchestration | Kubernetes |
| Managed Kubernetes | Amazon EKS |
| CI/CD | AWS CodePipeline, AWS CodeBuild |
| Cloud Provider | AWS |
| Version Control | GitHub |

---

## 🏗️ Architecture Overview

```

Developer
↓
GitHub Repository
↓
AWS CodePipeline (CI)
↓
Docker Image Build
↓
Amazon ECR
↓
Amazon EKS Cluster
↓
Kubernetes Pods (NGINX + React)
↓
AWS Load Balancer
↓
End Users

````

---

## 📂 Repository Structure

| File / Folder | Description |
|--------------|-------------|
| Dockerfile | Docker image configuration |
| buildspec.yml | CI build instructions |
| deployment.yaml | Kubernetes Deployment manifest |
| service.yaml | Kubernetes Service manifest |
| dist/ | React production build files |
| screenshots/ | Output verification screenshots |
| README.md | Project documentation |

---

## 🐳 Docker Implementation

- Uses **NGINX Alpine** image for lightweight production container
- Serves static React build files from `dist/`
- Optimized for performance and security

### Docker Workflow

1. Clone the GitHub repository  
2. Build Docker image  
3. Push Docker image to Amazon ECR  
4. Kubernetes pulls image from ECR during deployment  

---

## ☸️ Kubernetes Deployment (Amazon EKS)

### Deployment

- Defines desired pod replicas
- Uses Docker image from Amazon ECR
- Ensures high availability

### Service

- Type: **LoadBalancer**
- Exposes application publicly
- Automatically provisions AWS Load Balancer

---

## 🔐 AWS Security Configuration

- IAM role attached to EKS worker nodes
- Secure ECR access without hardcoded credentials
- Network access controlled using Security Groups
- Resources deployed inside AWS VPC

---

## 🔄 Continuous Integration with AWS CodePipeline

This project includes a **CI pipeline** to validate application builds on every GitHub push.

### CI Tools Used

| Purpose | AWS Service |
|-------|-------------|
| Source Control | GitHub |
| Pipeline Orchestration | AWS CodePipeline |
| Build Execution | AWS CodeBuild |
| Build Definition | buildspec.yml |

---

### CI Pipeline Stages

#### Source Stage
- GitHub repository connected using GitHub App
- Tracks `main` branch
- Automatically triggers on code push

#### Build Stage
- Uses AWS CodeBuild
- Installs dependencies
- Runs build commands
- Logs stored in CloudWatch

---

## 🧾 buildspec.yml

```yaml
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
````

---

## 🧪 Issues Faced and Solutions

| Issue                   | Solution                         |
| ----------------------- | -------------------------------- |
| Docker build failure    | Fixed build context and paths    |
| Missing build files     | Generated React production build |
| GitHub permission issue | Correct fork and authentication  |
| CI build failure        | Updated Node.js version          |
| Kubernetes access issue | Corrected kubeconfig             |

---

## ✅ Final Outcome

* Application successfully deployed on AWS EKS
* Docker images managed using Amazon ECR
* CI pipeline validates every commit
* End-to-end DevOps workflow implemented

---

## 📌 Conclusion

This project showcases a **real-world DevOps pipeline** using cloud-native technologies.
It highlights best practices in **containerization**, **Kubernetes orchestration**, and **CI automation** on AWS.

```


Ippo calm 😌 idhu **solid professional README** 💪
```
