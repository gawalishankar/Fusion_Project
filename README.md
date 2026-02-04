
# Dance Acadamy Project (Fusion) – AWS ECS Deployment

This repository contains a PHP + MySQL web application deployed on **AWS ECS (Fargate)** using **Docker, Amazon ECR, RDS, ALB, and GitHub Actions CI**.

---

## Architecture

GitHub → GitHub Actions (CI) → Amazon ECR → Amazon ECS (Fargate) → Application Load Balancer  
Database → Amazon RDS (MySQL)

---
## Fusion Project – Minikube Deployment

This repository contains a Node.js web application deployed on Kubernetes (Minikube) using Docker, Kubernetes Deployments & Services, and Prometheus + Grafana for monitoring.

---

## Architecture

GitHub → Docker → Minikube (Kubernetes)
                          ├─ Deployment
                          ├─ Service (NodePort)
                          └─ Prometheus + Grafana Monitoring

---

## Prerequisites

- Docker installed
- Minikube installed
- kubectl installed
- Helm installed (for Prometheus/Grafana)
- Git installed

## Verify:

docker --version
kubectl version --client
minikube version
helm version
git --version

---

## Step 1: Clone Repository

git clone https://github.com/gawalishankar/Fusion_Project.git
cd Fusion_Project

---

## Step 2: Start Minikube

minikube start --driver=docker
minikube addons enable ingress
kubectl get nodes

---

## Step 3: Build Docker Image

# Use Minikube Docker daemon
minikube docker-env | Invoke-Expression
docker build -t fusion-app:1.0 .
docker images

---

## Step 4: Deploy Application on Kubernetes

kubectl apply -f k8s/fusion-deployment.yaml
kubectl apply -f k8s/fusion-service.yaml
kubectl get pods
kubectl get svc
kubectl logs -l app=fusion

---

## Step 5: Access Application

minikube service fusion-service

---

## Step 8: Cleanup (Optional)

kubectl delete -f k8s/fusion-deployment.yaml
kubectl delete -f k8s/fusion-service.yaml
minikube stop
minikube delete
docker rmi fusion-app:1.0
