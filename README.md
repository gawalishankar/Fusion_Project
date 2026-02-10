## Fusion Project – Minikube Deployment

This repository contains a Node.js web application deployed on Kubernetes (Minikube) using Docker, Kubernetes Deployments & Services, and Prometheus + Grafana for monitoring.

---

## Architecture

GitHub → Docker → Minikube (Kubernetes)
                          ├─ Deployment
                          ├─ Service (NodePort)

---

## Prerequisites

- Docker installed
- Minikube installed
- kubectl installed
- Helm installed (for Prometheus/Grafana)
- Git installed

## Verify:
```python
- docker --version
- kubectl version --client
- minikube version
```
---

## Step 1: Clone Repository
```bash
- git clone https://github.com/gawalishankar/Fusion_Project.git
- cd Fusion_Project
```
---

## Step 2: Start Minikube
```bash
- minikube start --driver=docker
- minikube addons enable ingress
```
---

## Step 3: Build Docker Image
```bash
- docker build -t fusion-app:1.0 .
- docker images
```
---

## Step 4: Deploy Application on Kubernetes
```bash
- kubectl apply -f k8s/fusion-deployment.yaml
- kubectl apply -f k8s/fusion-service.yaml
```
---

## Step 5: Access Application
```bash
- minikube service fusion-service
```
---

## Step 8: Cleanup (Optional)
```bash
- kubectl delete -f k8s/fusion-deployment.yaml
- kubectl delete -f k8s/fusion-service.yaml
- minikube stop
- minikube delete
- docker rmi fusion-app:1.0
```
