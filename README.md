# product-microservice-kubernetes



# 🚀 GitOps Continuous Deployment with ArgoCD & Kubernetes

## 📌 Overview

This project demonstrates a complete GitOps workflow for deploying and managing a containerized application using ArgoCD and Kubernetes.

The system ensures that the Kubernetes cluster state is continuously synchronized with the desired state defined in a Git repository.

---

## 🧠 Architecture
<img width="1241" height="610" alt="image" src="https://github.com/user-attachments/assets/833168be-0427-48e7-9d4e-b735354d70e1" />

GitLab (YAML manifests)
↓
ArgoCD (Continuous Delivery)
↓
Kubernetes Cluster (Minikube)
↓
Deployment → ReplicaSet → Pods → Service

---

## ⚙️ Technologies Used

* Kubernetes (Minikube)
* ArgoCD
* Docker
* GitLab (as GitOps repository)
* YAML (Kubernetes manifests)

---

## 🔄 GitOps Workflow
<img width="1884" height="867" alt="image" src="https://github.com/user-attachments/assets/4de8b7f5-deb7-49ec-aee6-03762e977d8b" />

1. Developer updates Kubernetes manifests in GitLab
2. ArgoCD detects changes automatically
3. ArgoCD syncs the cluster state with Git
4. Kubernetes applies the changes
5. Application updates without manual intervention

<img width="1897" height="883" alt="image" src="https://github.com/user-attachments/assets/1c10af4d-4d83-4667-84b3-9785af95157d" />


---

## 📦 Features

* 🔄 Automatic synchronization (Auto-Sync enabled)
* 📈 Dynamic scaling (replica updates via Git)
* ♻️ Self-healing (cluster state reconciliation)
* 🚀 Continuous Deployment without kubectl
* 📁 Infrastructure as Code (IaC)

---

---

## ▶️ How to Run

### 1. Start Minikube

```bash
minikube start
```

### 2. Install ArgoCD

```bash
kubectl create namespace argocd
kubectl apply -n argocd -f https://raw.githubusercontent.com/argoproj/argo-cd/stable/manifests/install.yaml
```

### 3. Access ArgoCD

```bash
kubectl port-forward svc/argocd-server -n argocd 8080:443
```

### 4. Login

* Username: admin
* Password:

```bash
kubectl -n argocd get secret argocd-initial-admin-secret \
-o jsonpath="{.data.password}" | base64 --decode
```

---




