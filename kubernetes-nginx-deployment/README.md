# 🚀 Kubernetes Nginx Application Deployment

![Kubernetes](https://img.shields.io/badge/Kubernetes-Orchestration-326CE5?logo=kubernetes&logoColor=white)
![Docker](https://img.shields.io/badge/Container-Nginx-009639?logo=nginx&logoColor=white)
![YAML](https://img.shields.io/badge/Configuration-YAML-red)
![Platform](https://img.shields.io/badge/Platform-Linux%20%7C%20Windows-blue)

## 📌 Project Overview

This project demonstrates the deployment and management of a containerized Nginx application using Kubernetes.

It showcases Kubernetes orchestration concepts, including multi-replica Deployments, Service discovery, Namespace isolation, resource management, and application health monitoring.

## 🏗️ Kubernetes Architecture

![Kubernetes Nginx Deployment Architecture](..images/kubernetes-architecture.png)

The architecture demonstrates how Kubernetes manages two Nginx replicas inside a dedicated Namespace and exposes the application through a NodePort Service.

## 🛠️ Technologies Used

- Kubernetes
- Docker
- Nginx
- YAML
- kubectl
- Linux
- Windows 11

## ⚙️ Key Features

- **Namespace Isolation:** Uses a dedicated Namespace named `nginx-demo`.
- **Deployment Management:** Deploys Nginx with two replicas.
- **Service Discovery:** Exposes the application using a NodePort Service.
- **Health Monitoring:** Configures readiness and liveness probes.
- **Resource Management:** Defines CPU and memory requests and limits.
- **Container Orchestration:** Uses Kubernetes to manage application Pods.

## 📂 Project Structure

```text
kubernetes-nginx-deployment/
│
├── README.md
├── images/
│   └── kubernetes-architecture.png
│
└── k8s/
    ├── namespace.yaml
    ├── deployment.yaml
    └── service.yaml
```

## 🚀 Deployment Instructions

### 1. Prerequisites

Install and configure:

- Docker Desktop with Kubernetes enabled, or Minikube
- kubectl

Verify Kubernetes connectivity:

```bash
kubectl cluster-info
```

### 2. Clone the Repository

```bash
git clone https://github.com/vijaycloudops/kubernetes-nginx-deployment.git
```

```bash
cd kubernetes-nginx-deployment
```

### 3. Deploy Kubernetes Resources

Apply the Namespace:

```bash
kubectl apply -f k8s/namespace.yaml
```

Apply the Deployment:

```bash
kubectl apply -f k8s/deployment.yaml
```

Apply the Service:

```bash
kubectl apply -f k8s/service.yaml
```

### 4. Verify Deployment

Check Pods:

```bash
kubectl get pods -n nginx-demo
```

Check Deployment:

```bash
kubectl get deployments -n nginx-demo
```

Check Services:

```bash
kubectl get services -n nginx-demo
```

### 5. Access the Nginx Application

For Docker Desktop Kubernetes or a suitable local cluster configuration, open:

```text
http://localhost:30080
```

Alternatively, use port forwarding:

```bash
kubectl port-forward service/nginx-service 8080:80 -n nginx-demo
```

Then open:

```text
http://localhost:8080
```

## 🧹 Cleanup

Remove all project resources:

```bash
kubectl delete namespace nginx-demo
```

## 🎯 Skills Demonstrated

- Kubernetes application deployment
- Container orchestration
- Kubernetes Services and networking
- Namespace management
- Application health checks
- Resource requests and limits
- Infrastructure troubleshooting

## 👨‍💻 Author

**Vijay Kumar Kunja**

GitHub: [vijaycloudops](https://github.com/vijaycloudops)

---

⭐ If you find this project useful, feel free to explore the repository and its Kubernetes manifests.
