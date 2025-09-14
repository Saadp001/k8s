# ☸️ Kubernetes Architecture – Control Plane & Data Plane

This repository contains my notes and diagram on **Kubernetes Architecture**, as part of my journey to learn Kubernetes in depth.

---

## 🚀 Why Kubernetes?
- **Docker** helps us build and run containers.  
- **Kubernetes (K8s)** manages those containers **at scale**.  

It provides:  
✅ Scaling (up & down)  
✅ Self-healing (restarts failed Pods, reschedules on healthy nodes)  
✅ Load balancing & service discovery  
✅ Declarative configuration ("desired state")  

---

## 🧠 Control Plane (Master Node)
The **Control Plane** is the "brain" of Kubernetes. It manages the cluster, makes global decisions, and ensures the desired state matches the actual state.

### **Key Components**
- **API Server**
  - Entry point for all communication into the cluster.  
  - Exposes the Kubernetes API (used by `kubectl`, UI, or REST calls).  
  - Validates and processes requests.  

- **etcd**
  - A distributed key-value store.  
  - Stores **all cluster data** (current state, configs, secrets, service discovery info).  
  - Think of it as Kubernetes’ "database."  

- **Scheduler**
  - Watches for new Pods with no assigned node.  
  - Decides which **worker node** will run them, based on resource availability and constraints.  

- **Controller Manager**
  - Runs various controllers to maintain the desired state.  
  - Examples:  
    - **ReplicaSet Controller** → Ensures the right number of Pods are running.  
    - **Node Controller** → Detects & replaces failed nodes.  
    - **Endpoints Controller** → Manages endpoint objects for services.  

- **Cloud Controller Manager**
  - Integrates Kubernetes with cloud providers (AWS, GCP, Azure).  
  - Manages resources like load balancers, storage volumes, and networking.  

---

## ⚙️ Data Plane (Worker Nodes)
The **Worker Nodes** are where actual applications (containers) run. They execute workloads as instructed by the Control Plane.

### **Key Components**
- **Kubelet**
  - An agent running on each worker node.  
  - Communicates with the API Server.  
  - Ensures containers described in Pod specs are running.  
  - Reports node & Pod status back to the Control Plane.  

- **Container Runtime**
  - The actual software responsible for running containers.  
  - Kubernetes does not run containers by itself.  
  - Supported runtimes: **Docker**, containerd, CRI-O.  

- **Kube-proxy**
  - Handles node-level networking.  
  - Routes traffic between Pods and Services.  
  - Implements load balancing.  

- **Pods**
  - The smallest deployable unit in Kubernetes.  
  - Usually runs **a single container** (sometimes multiple tightly coupled containers).  
  - Encapsulates the application container, storage, and networking config.  

---

## 🔄 Control Plane vs Data Plane
- **Control Plane (Master)** → Decides what should happen.  
- **Data Plane (Workers)** → Executes those decisions.  

👉 Analogy:  
- Control Plane = **Air Traffic Control** 🛫 (assigns flights, ensures safety).  
- Data Plane = **Planes (Workers)** ✈️ (actually carry passengers).  

---

## 📊 Diagram
Here’s a simple visualization of the architecture:  

![Kubernetes Architecture](./architecture-diagram.png)  

---

## ✨ Key Takeaways
- Docker = Containerization 🐳  
- Kubernetes = Container Orchestration ☸️  
- Kubernetes separates **decision-making (Control Plane)** from **execution (Data Plane)**.  
- Ensures applications are always **running, scalable, and resilient** in production.  

---

### 📌 Learning in Public
I’ll keep updating this repo with more **Kubernetes concepts** as I go deeper.  

#Kubernetes #DevOps #Docker #CloudComputing #LearningInPublic
