# DevSecOps CI/CD: Deploying a Secure Hotstar Clone

## Overview

This project demonstrates the implementation of **DevSecOps CI/CD pipeline** for securely deploying a **Hotstar Clone** using **AWS, Docker, Kubernetes, Jenkins, Terraform, and SonarQube**. It follows security best practices to automate infrastructure provisioning, vulnerability scanning, and container orchestration.
## Blog for Step by Step Process
https://mrcloudbook.com/devsecops-ci-cd-deploying-a-secure-hotstar-clone-even-if-youre-not-a-pro/

## Features

- **CI/CD Pipeline**: Configured using **Jenkins** for automated build, test, and deployment.
- **Security Integration**: Uses **SonarQube, OWASP, and Docker Scout** for static code analysis, security checks, and container vulnerability scanning.
- **Infrastructure as Code (IaC)**: Automated provisioning using **Terraform**.
- **Containerized Deployment**: Application is deployed using **Docker** and orchestrated via **AWS EKS (Kubernetes)**.
- **Automated Quality Gates**: Integrated **SonarQube** for code quality assessment.

## Prerequisites

Before setting up this project, ensure you have:

- An **AWS Account** with appropriate permissions
- **Basic knowledge of DevSecOps** principles
- Familiarity with **Docker, Jenkins, Java, Terraform, Kubernetes (kubectl), AWS CLI, and Docker Scout**
- Installed tools: **Docker, Terraform, AWS CLI, Jenkins, SonarQube, and Kubernetes (kubectl)**

## Deployment Steps

### Step 1: Setting up AWS EC2 Instance

1. Create an **EC2 instance** with **Ubuntu AMI (t2.large, 30GB storage)**.
2. Assign an **IAM role** with **Admin access** for learning purposes.

### Step 2: Installing Required Tools

Automate the installation of essential tools on the EC2 instance:

```bash
sudo apt update -y
sudo apt install -y docker.io jenkins terraform awscli kubectl
```

Run a **SonarQube** container:

```bash
docker run -d --name sonar -p 9000:9000 sonarqube:lts-community
```

### Step 3: Configuring Jenkins for CI/CD

1. Install required **Jenkins Plugins**: Terraform, SonarQube, NodeJS, OWASP, Docker.
2. Add **SonarQube credentials** in Jenkins.
3. Configure Jenkins **Pipeline Jobs** for:
   - Provisioning **AWS EKS** using **Terraform**
   - Deploying the **Hotstar Clone**
   - Running **security checks** (SonarQube, OWASP, Docker Scout)
   - Building and pushing **Docker images**
   - Deploying application to **Kubernetes Cluster**

### Step 4: Kubernetes Deployment

1. Apply Kubernetes manifests for **deployment** and **service**:

```bash
kubectl apply -f deployment.yml
kubectl apply -f service.yml
```

2. Retrieve the **Load Balancer URL** to access the application.

### Step 5: Clean-Up

To delete the AWS resources:

```bash
terraform destroy --auto-approve
```

Terminate the **EC2 instance** and delete the **IAM Role**.

## Tools & Technologies Used

- **AWS** (EC2, EKS, IAM, S3)
- **Jenkins** (CI/CD Pipeline)
- **Docker & Kubernetes** (Containerization & Orchestration)
- **Terraform** (Infrastructure as Code)
- **SonarQube, OWASP, Docker Scout** (Security Analysis)
- **Node.js, Java** (Application development)
- **Git & GitHub** (Version Control)

## Project Repository

🔗 [GitHub Repository](https://github.com/Kritagya-web/Hotstar-DevOps-Project-Kubernetes-AWS-EKS)

---

## Credit

This project was inspired and greatly enhanced by the **detailed documentation provided by [Mr. Cloud Book](https://mrcloudbook.com)**. Their in-depth explanation helped me understand **DevSecOps, CI/CD, and Kubernetes deployment** in detail. Huge thanks for sharing such **valuable content** for the community!

---

## Connect with Me

For any questions or discussions, feel free to reach out:

- **GitHub**: [Kritagya-web](https://github.com/Kritagya-web/)
- **LinkedIn**: [Kritagya Kumra](https://www.linkedin.com/in/kritagya-kumra/)
- **Portfolio**: [Portfolio](https://kritagyakumraportfolio.netlify.app/)

---

🚀 **Created with love ❤️ by Kritagya. Happy Learning & Secure Deployments!**
🚀 **Show some ❤️ by starring at some of the repositories!**
