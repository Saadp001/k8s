# 🚀 Kubernetes Architecture – Control Plane vs Data Plane

As part of my Kubernetes learning journey, I explored the **Kubernetes Architecture** and how it orchestrates containers at scale.

---

## 🧠 Control Plane (Master Node)
The Control Plane is responsible for managing the cluster and making global decisions.

- **API Server** → Entry point for all cluster communication  
- **etcd** → Stores cluster state (key-value store)  
- **Scheduler** → Decides which node runs a Pod  
- **Controller Manager** → Ensures desired state matches actual state  
- **Cloud Controller Manager** → Connects Kubernetes with cloud providers  

---

## ⚙️ Data Plane (Worker Nodes)
Worker Nodes are where applications actually run.

- **Kubelet** → Node agent, ensures Pods are running as expected  
- **Container Runtime** → Runs containers (Docker, containerd, CRI-O)  
- **Kube-proxy** → Manages networking and load balancing  
- **Pods** → Smallest deployable unit (encapsulates one or more containers)  

---

## 📊 Architecture Diagram
Here’s a simple visualization of the flow:

![Kubernetes Architecture](./k8s-architecture.png)

---

## ✨ Key Takeaway
Kubernetes is much more than running containers – it provides:  
- Scalability ⚡  
- Self-healing ❤️‍🔥  
- Service discovery & load balancing 🌍  
- Automated rollouts and rollbacks 🔄  

I’m excited to continue diving deeper into #Kubernetes and #DevOps concepts 🚀

---

### 📌 Stay Tuned
I’ll keep updating this repo with my **K8s learning journey** step by step.  

#K8s #DevOps #CloudComputing #Containers #LearningInPublic
