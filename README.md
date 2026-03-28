# 🚀 Dockerized FastAPI Microservice with Kubernetes

![Docker](https://img.shields.io/badge/Docker-Containerized-blue?logo=docker)
![Kubernetes](https://img.shields.io/badge/Kubernetes-Orchestrated-blue?logo=kubernetes)
![Python](https://img.shields.io/badge/Python-3.11-yellow?logo=python)
![FastAPI](https://img.shields.io/badge/FastAPI-Framework-green)

---

## 📌 Overview
This project demonstrates building, containerizing, and deploying a FastAPI microservice using Docker and Kubernetes. It includes scaling, rolling updates, and production-ready features such as health checks and resource management.

---

## 🛠️ Tech Stack
- Python (FastAPI)
- Docker
- Kubernetes
- Uvicorn

---

## ⚙️ Features
- REST API microservice
- Docker containerization
- Kubernetes Deployment & Service
- Horizontal scaling (3 replicas)
- Rolling updates (v1 → v2)
- Health check endpoint
- Readiness & Liveness probes ⭐
- CPU resource requests & limits ⭐
- ClusterIP Service + Port Forwarding ⭐

---

## 📂 Project Structure

```
hello-microservice/
├── app.py
├── requirements.txt
├── Dockerfile
└── k8s/
    ├── deployment.yaml
    └── service.yaml
```

---

## 🌐 API Endpoints

| Endpoint | Description |
|----------|-------------|
| `/` | Returns version message |
| `/health` | Health check endpoint |

---

## 🐳 Docker

### Build Image
```bash
docker build -t hamizs/hello-microservice:2.0 .
```

### Push to Docker Hub
```bash
docker push hamizs/hello-microservice:2.0
```

🔗 Docker Hub:  
https://hub.docker.com/r/hamizs/hello-microservice

---

## ☸️ Kubernetes

### Apply Deployment & Service
```bash
kubectl apply -f k8s/deployment.yaml
kubectl apply -f k8s/service.yaml
```

### Check Resources
```bash
kubectl get deployments
kubectl get pods
kubectl get svc
```

---

## 🔄 Scaling

```bash
kubectl scale deployment hello-microservice --replicas=3
```

---

## 🔁 Rolling Update

```bash
kubectl apply -f k8s/deployment.yaml
kubectl rollout status deployment hello-microservice
```

---

## 🔗 Access the Service

```bash
kubectl port-forward svc/hello-microservice-service 8080:80
```

Test endpoints:

```bash
curl http://localhost:8080
curl http://localhost:8080/health
```

---

## 📊 Example Output

```json
{"message": "Hello from version 2!"}
```

```json
{"status": "ok"}
```

---

## ⭐ Bonus Features Implemented

- Readiness Probe (`/health`)
- Liveness Probe (`/health`)
- CPU Requests: `100m`
- CPU Limits: `500m`
- ClusterIP Service with port-forward access

---

## 📌 Key Concepts Demonstrated

- Containerization with Docker
- Kubernetes orchestration
- Horizontal scaling
- Rolling updates with zero downtime
- Health monitoring (liveness/readiness probes)
- Resource management (CPU limits/requests)

---

## 👨‍💻 Author
Hamiz Siddiqui

---

## 🚀 Why This Project Matters
This project demonstrates real-world cloud-native development practices used in modern DevOps environments, making it a strong portfolio piece for backend, cloud, or DevOps roles.
