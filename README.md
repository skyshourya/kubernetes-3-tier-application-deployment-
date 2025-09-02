# Kubernetes 3-Tier Application Deployment

This repository demonstrates how to deploy a **3-tier application (Frontend + Backend + Database)** on Kubernetes using Dockerized components and Kubernetes manifests.

It’s designed as a practical example for learning how to containerize applications, deploy them to Kubernetes, and connect services across tiers in a cluster.

---

## 📌 Overview

The project consists of:

- **Frontend** – A web interface for users (e.g., React or static HTML/JS).  
- **Backend** – An API service (e.g., Node.js/Express) handling business logic.  
- **Database** – A persistent data storage service (e.g., MongoDB or SQL).  

Each tier runs in its own container, and Kubernetes manages their deployment, scaling, and networking.

---

## 🚀 Features

- Kubernetes **Deployments** for application components  
- **Services** for internal/external communication  
- (Optional) **Ingress** or **LoadBalancer** for external access  
- Environment variables & config separation  
- Ready-to-use manifests for quick deployment  

---

## 📂 Project Structure

```bash
├── App_code/                # Application source code
│   ├── frontend/            # Frontend code (UI)
│   └── backend/             # Backend code (API)
├── kubernetes_files/        # Kubernetes manifests
│   ├── Backend/             # Backend Deployment & Service
│   ├── Frontend/            # Frontend Deployment & Service (if present)
│   └── Database/            # Database Deployment, Service, Secrets
└── README.md                # Project documentation






---

## ✅ Prerequisites

Before you begin, make sure you have:

- [Docker](https://docs.docker.com/get-docker/) installed  
- Access to a Kubernetes cluster (Minikube, kind, EKS, GKE, etc.)  
- [`kubectl`](https://kubernetes.io/docs/tasks/tools/) configured for your cluster  
- A container registry account (e.g., Docker Hub or AWS ECR)  

---

## ⚡ Getting Started

### 1. Clone this repository

```bash
git clone https://github.com/skyshourya/kubernetes-3-tier-application-deployment-.git
cd kubernetes-3-tier-application-deployment-



# Frontend
cd App_code/frontend
docker build -t your-registry/3tier-frontend:latest .
docker push your-registry/3tier-frontend:latest

# Backend
cd ../backend
docker build -t your-registry/3tier-backend:latest .
docker push your-registry/3tier-backend:latest



kubectl create namespace three-tier
kubectl config set-context --current --namespace=three-tier


# Deploy Database
kubectl apply -f kubernetes_files/Database/

# Deploy Backend
kubectl apply -f kubernetes_files/Backend/

# Deploy Frontend
kubectl apply -f kubernetes_files/Frontend/



kubectl get all
kubectl get svc


