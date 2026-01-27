
# ☸️ Introduction to Kubernetes

_(Explained simply, deeply, and practically)_

---

## 1️⃣ What is Kubernetes?

### One-line definition (EXAM GOLD ⭐)

> **Kubernetes is a container orchestration platform that automates deployment, scaling, and management of containerized applications.**

---

### Why do we even need Kubernetes?

Docker can:

- Run containers ✔️
    
- Build images ✔️
    

But Docker **cannot easily**:

- Run **100s of containers**
    
- Restart failed containers automatically
    
- Scale up/down based on traffic
    
- Do zero-downtime updates
    

👉 **Kubernetes solves these problems**

---

## 2️⃣ What Problems Kubernetes Solves

### 🚀 Core Features (VERY IMPORTANT)

#### 🔁 High Availability

- App is distributed across **multiple nodes**
    
- If one node dies → app stays up
    

---

#### 📈 Auto-Scaling

- More users → more Pods
    
- Less traffic → fewer Pods
    
- Automatic, not manual
    

---

#### 🩺 Self-Healing

- Container crashes? → restarted
    
- Node dies? → Pods rescheduled
    
- You don’t panic — Kubernetes fixes it
    

---

#### 🔄 Easy Rollouts & Rollbacks

- Update app **without downtime**
    
- New version fails? → rollback instantly
    

---

### Why Kubernetes? (Short Answer)

> **Because production systems need automation, resilience, and scale.**

---

## 3️⃣ Kubernetes Cluster Architecture (CORE CONCEPT)

A Kubernetes system is called a **cluster**.

### A cluster has **2 main parts**:

```
Control Plane (Brain)
Worker Nodes (Muscles)
```

---

## 4️⃣ Control Plane (The Brain 🧠)

The **Control Plane** manages the **entire cluster state**.

### Components you MUST remember:

---

### 🔹 API Server

- Entry point for everything
    
- `kubectl apply` talks here
    

👉 Front door of Kubernetes

---

### 🔹 etcd

- Key-value database
    
- Stores:
    
    - YAML configs
        
    - Cluster state
        
    - Desired state
        

👉 Kubernetes memory 🧠

---

### 🔹 Scheduler

- Decides:
    
    > “Which Pod runs on which node?”
    

Checks:

- CPU
    
- Memory
    
- Node health
    

---

### 🔹 Controller Manager

- Watches cluster state
    
- Fixes mismatches
    

Example:

- You want 3 Pods
    
- Only 2 running
    
- Controller creates 1 more
    

---

## 5️⃣ Worker Nodes (The Muscles 💪)

Worker Nodes actually **run your apps**.

### Each Worker Node has:

---

### 🔹 Kubelet

- Agent on each node
    
- Talks to Control Plane
    
- Ensures containers are running
    

---

### 🔹 Kube-proxy

- Handles networking
    
- Routes traffic to Pods
    

---

### 🔹 Container Runtime

- Runs containers
    
- Examples:
    
    - Docker
        
    - containerd
        

---

## 6️⃣ Control Plane ↔ Worker Nodes (Big Picture)

- Control Plane decides **WHAT should happen**
    
- Worker Nodes do **THE WORK**
    

---

## 7️⃣ Kubernetes Objects (BUILDING BLOCKS)

You define Kubernetes objects using **YAML files**.

---

## 🔹 Pod (SMALLEST UNIT)

### Definition:

> A **Pod** is the smallest deployable unit in Kubernetes.

- Contains **1 or more containers**
    
- Containers share:
    
    - Network
        
    - Storage
        

📌 You **never scale Pods directly** in production.

---

## 🔹 Deployment (MOST USED)

### Definition:

> A Deployment manages Pods and ensures the desired number is running.

Handles:

- Replicas
    
- Rolling updates
    
- Rollbacks
    
- Self-healing
    

📌 **Always use Deployment**, not raw Pods.

---

## 🔹 Service

### Problem:

Pods have:

- Random IPs
    
- Can die anytime
    

### Solution:

> **Service provides a stable network endpoint**

Types:

- **ClusterIP** → internal
    
- **NodePort** → external via node IP
    
- **LoadBalancer** → cloud load balancer
    

---

## 8️⃣ ConfigMaps & Secrets

---

### 🔹 ConfigMap

- Stores **non-sensitive config**
    
- Example:
    
    - App mode
        
    - Feature flags
        

Keeps config **outside code**

---

### 🔹 Secret

- Stores **sensitive data**
    
- Example:
    
    - Passwords
        
    - API keys
        

Base64 encoded

---

## 🔹 Namespace

- Logical grouping
    
- Useful for:
    
    - Teams
        
    - Environments (dev, prod)
        

---

## 9️⃣ How Kubernetes Works (YAML → Running Pod)

### Step-by-step FLOW ⭐

1️⃣ Write YAML  
“I want 3 Pods”

2️⃣ `kubectl apply`  
Sent to **API Server**

3️⃣ Stored in **etcd**

4️⃣ Scheduler assigns Pods to nodes

5️⃣ Kubelet starts containers

---

## 🔟 Self-Healing (VERY IMPORTANT)

### 🔍 Liveness Probe

**Question:** _Is the app running?_

- If fails → container restarted
    

---

### 🚦 Readiness Probe

**Question:** _Is the app ready for traffic?_

- If fails → traffic stopped
    
- Pod not killed
    

---

## 1️⃣1️⃣ Real-World Usage

Used by:

- Google (GKE)
    
- Netflix
    
- Uber
    
- **PickMe** 🚕
    

Handles:

- Millions of requests
    
- CI/CD pipelines
    
- Massive scaling
    

---

# 🧪 Kubernetes LAB (Hands-On Explained)

---

## Part 0️⃣: Install & Verify Minikube

```bash
minikube start
kubectl get nodes
```

Expected:

- 1 node
    
- Status: Ready
    

---

## Part 1️⃣: Running Pods

---

### Create Pod YAML (`nginx-pod.yaml`)

```yaml
apiVersion: v1
kind: Pod
metadata:
  name: my-nginx-pod
spec:
  containers:
  - name: nginx
    image: nginx
    ports:
    - containerPort: 80
```

---

### Apply Pod

```bash
kubectl apply -f nginx-pod.yaml
kubectl get pods
```

---

### Access Pod

```bash
kubectl port-forward pod/my-nginx-pod 8080:80
```

🌐 Visit:

```
http://localhost:8080
```

---

### Delete Pod

```bash
kubectl delete pod my-nginx-pod
```

---

## Part 2️⃣: Deployments (REAL WORLD)

---

### Create Deployment YAML

```yaml
apiVersion: apps/v1
kind: Deployment
metadata:
  name: web-deployment
spec:
  replicas: 3
  selector:
    matchLabels:
      app: web
  template:
    metadata:
      labels:
        app: web
    spec:
      containers:
      - name: web
        image: nginx
        ports:
        - containerPort: 80
```

---

### Apply & Verify

```bash
kubectl apply -f web-deployment.yaml
kubectl get deployments
kubectl get pods
```

---

## Part 3️⃣: Exposing with Service

```bash
kubectl expose deployment web-deployment --type=NodePort --port=80
kubectl get svc
```

If Minikube:

```bash
minikube service web-deployment
```

---

## Part 4️⃣: Scaling

```bash
kubectl scale deployment web-deployment --replicas=5
kubectl get pods
```

🔥 Kubernetes creates Pods automatically

---

## Part 5️⃣: Rollouts & Rollbacks

### Update Image

```bash
kubectl set image deployment/web-deployment web=nginx:latest
kubectl rollout status deployment/web-deployment
```

---

### Rollback

```bash
kubectl rollout undo deployment/web-deployment
```

---

## Part 6️⃣: ConfigMaps & Secrets (Syntax)

```bash
kubectl create configmap app-config --from-literal=APP_MODE=dev
kubectl create secret generic db-secret --from-literal=password=12345
```

---

## Part 7️⃣: Cleanup

```bash
kubectl delete -f web-deployment.yaml
kubectl delete svc web-deployment
kubectl delete configmap app-config
kubectl delete secret db-secret
```

---

## 🧠 FINAL THEORY SUMMARY (EXAM READY)

✔️ Kubernetes orchestrates containers  
✔️ Control Plane manages state  
✔️ Worker Nodes run apps  
✔️ Pods are smallest units  
✔️ Deployments manage replicas  
✔️ Services expose apps  
✔️ YAML defines desired state

---

If you want next:

- 🧾 **Exam notes (1–2 pages)**
    
- ❓ **MCQs + answers**
    
- 🧩 **Kubernetes vs Docker (interview)**
    
- 🚀 **K8s for Java / Spring Boot**
    
- ☁️ **Kubernetes on Cloud (GKE / EKS)**
    

Just say the word 😄