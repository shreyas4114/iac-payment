# iac-payment

## 📎 Related Repositories

➡️ [payment-actions](https://github.com/shreyas4114/payment_actions): Microservices application deployed to this EKS cluster.

Infrastructure as a Code (IaaC) for deploying a production-ready AWS EKS (Elastic Kubernetes Service) cluster using Terraform and GitHub Actions.

## 🚀 Overview

This repository automates the creation and configuration of the Kubernetes infrastructure required to host the `Payment` microservices application. It provisions:

- EKS Cluster
- VPC and Networking components
- IAM roles and policies
- Kubernetes provider setup
- Ingress Controller installation

---

## ⚙️ Tech Stack

- **Terraform** for Infrastructure as Code
- **AWS** (EKS, IAM, VPC)
- **GitHub Actions** for CI/CD
- **kubectl** for Kubernetes interaction
- **NGINX Ingress Controller**

---

## 🔄 GitHub Actions Workflow

The GitHub Actions workflow (`.github/workflows/tarraform.yaml`) automatically:

1. Initializes Terraform with remote S3 backend
2. Formats and validates code
3. Generates and applies a Terraform plan (on `main` branch push)
4. Updates the `kubeconfig` with the new EKS cluster
5. Installs NGINX Ingress Controller on the cluster

Trigger Paths:
- Push or PR to `main` or `stage` branch under `terraform/`

---

## 🛠️ Prerequisites

- AWS account with appropriate IAM permissions
- An S3 bucket for remote Terraform state
- GitHub repository secrets:
  - `AWS_ACCESS_KEY_ID`
  - `AWS_SECRET_ACCESS_KEY`
  - `BUCKET_TF_STATE`

---

## 📦 Outputs

After successful execution:
- EKS cluster endpoint and kubeconfig are configured
- Ingress controller is running and ready to accept microservices

---
