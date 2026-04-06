# 🚀 EKS Deployment Automation using Jenkins & Terraform

## 📌 Overview

This project demonstrates an end-to-end DevOps workflow to provision and manage an Amazon EKS (Elastic Kubernetes Service) cluster using Terraform, automated through a Jenkins CI/CD pipeline.

It enables infrastructure provisioning, scaling, and teardown using a parameterized pipeline with manual approval, simulating real-world production workflows.

---

## 🧱 Tech Stack

* **Cloud**: AWS (EKS, EC2, IAM, VPC)
* **Infrastructure as Code**: Terraform
* **CI/CD**: Jenkins
* **Container Orchestration**: Kubernetes (EKS)
* **Version Control**: Git & GitHub
* **Scripting**: Bash

---

## ⚙️ Key Features

* 🚀 Automated EKS cluster provisioning using Terraform
* 🔄 Jenkins pipeline for infrastructure lifecycle management
* 📦 Managed Node Groups for Kubernetes workloads
* 🔐 IAM roles and policies for secure access control
* 📈 Scalable node configuration
* ⏱️ Manual approval step before infrastructure changes
* 🔥 Support for both **create (apply)** and **destroy** actions

---

## 🏗️ Architecture

```
Developer → GitHub → Jenkins Pipeline → Terraform → AWS EKS Cluster → Node Group
```

---

## 🔄 CI/CD Workflow

1. Developer pushes code to GitHub
2. Jenkins pipeline is triggered
3. Terraform initializes and validates configuration
4. Terraform plan is generated
5. Manual approval is required
6. Based on input:

   * `apply` → creates EKS cluster
   * `destroy` → deletes infrastructure

---


## ☁️ Infrastructure Details

### 🔹 EKS Cluster

* Managed Kubernetes control plane
* Uses IAM role for cluster permissions

### 🔹 Node Group

* EC2 instances as worker nodes
* Auto-scaling configuration:

  * Min: 1
  * Max: 2
  * Desired: 1

### 🔹 Networking

* Uses default VPC
* Public subnets for cluster and nodes

---

## 🚀 Setup Instructions

### 1️⃣ Clone Repository

```bash
git clone https://github.com/Manikandan-Premkumar/Deploy.git
cd Deploy
```

---

### 2️⃣ Configure Jenkins

* Install required plugins:

  * Git
  * Pipeline
  * Docker (optional)
* Add AWS credentials in Jenkins:

  * `AWS_ACCESS_KEY_ID`
  * `AWS_SECRET_ACCESS_KEY`

---

### 3️⃣ Run Pipeline

* Select action:

  * `apply` → create infrastructure
  * `destroy` → delete infrastructure
* Approve when prompted

---

### 4️⃣ Configure kubectl (after apply)

```bash
aws eks --region us-east-1 update-kubeconfig --name EKS_CLOUD
kubectl get nodes
```

---



This project is licensed under the MIT License.
