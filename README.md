# 📦 Kubernetes Learning Repo

This repository contains a simple microservice setup deployed on **Kubernetes using Minikube**. It’s designed as a learning playground to explore core K8s concepts like Deployments, Services, Ingress, ConfigMaps, and Secrets.

---

## 🚀 Stack Overview

| Component    | Description                               |
| ------------ | ----------------------------------------- |
| `webapp`     | Node.js backend (containerized)           |
| `mongo`      | MongoDB database (containerized)          |
| `Ingress`    | Routes external traffic to the webapp     |
| `Services`   | Internal load balancing (webapp ↔ mongo)  |
| `Secrets`    | Stores DB username/password securely      |
| `ConfigMaps` | Stores environment configs (e.g., DB URL) |
| `Minikube`   | Local Kubernetes cluster                  |

---

## 🧪 How to Run (with Minikube)

1. **Start Minikube**

   ```bash
   minikube start
   ```

2. **Enable Ingress (if not already)**

   ```bash
   minikube addons enable ingress
   ```

3. **Apply all manifests**

   ```bash
   kubectl apply -f .
   ```

4. **Check running resources**

   ```bash
   kubectl get pods,svc,ingress
   ```

5. **Access the app**

   - Add the following entry to your `/etc/hosts` file (Mac/Linux):

     ```
     127.0.0.1 webapp.local
     ```

   - Or use the Minikube IP directly:

     ```bash
     minikube ip
     ```

   - Then visit in your browser:

     ```
     http://webapp.local:30100
     OR
     http://<minikube-ip>:30100
     ```

---

## ✅ What This Covers

- [x] Deployments & ReplicaSets
- [x] ClusterIP & NodePort Services
- [x] Ingress routing with hostname
- [x] Secrets and ConfigMaps
- [x] Environment variable injection into containers
- [x] Local Kubernetes development with Minikube

---

## 🧠 Goal

The goal of this project is to build hands-on experience with Kubernetes by simulating a real-world setup using a basic Node.js + MongoDB application. This setup provides a foundation for learning more advanced concepts such as:

- Spring Boot deployments
- Liveness & readiness probes
- Persistent volumes (PVCs)
- CI/CD with Helm or GitHub Actions
- Monitoring & observability (Prometheus, Grafana)

---

## 📌 Prerequisites

- [Docker](https://www.docker.com/)
- [Minikube](https://minikube.sigs.k8s.io/docs/start/)
- [kubectl](https://kubernetes.io/docs/tasks/tools/)

> This is generated with ChatGPT, could be slightly wrong.
