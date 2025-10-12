## ☸️ Kubernetes (K8s)

### 🧩 Keywords
- Cluster Architecture  
  - Control Plane (API Server, Scheduler, Controller Manager, etcd)  
  - Node Components (kubelet, kube-proxy, container runtime)  
- Pod / ReplicaSet / Deployment / StatefulSet / DaemonSet / Job / CronJob  
- Service (ClusterIP, NodePort, LoadBalancer, ExternalName)  
- Ingress / Ingress Controller  
- Namespace / Context / kubeconfig  
- ConfigMap / Secret  
- Volume / PersistentVolume (PV) / PersistentVolumeClaim (PVC)  
- StorageClass / Dynamic Provisioning  
- CNI (Container Network Interface)  
- Cluster Networking (Pod-to-Pod, Pod-to-Service, Service-to-External)  
- kube-proxy / iptables / IPVS  
- DNS (CoreDNS)  
- Resource Requests & Limits / QoS Classes  
- Liveness Probe / Readiness Probe / Startup Probe  
- Horizontal Pod Autoscaler (HPA) / Vertical Pod Autoscaler (VPA)  
- RBAC (Role-Based Access Control)  
- Admission Controller / Mutating & Validating Webhook  
- Taints / Tolerations / NodeSelector / Affinity  
- Labels / Annotations / Selectors  
- Helm / Operator / CRD (Custom Resource Definition)  
- kubeconfig / Contexts / ServiceAccount / Token  
- Observability: kubectl logs, events, metrics-server, Prometheus, Grafana  

---

### 💬 Common Interview Questions
- What is the difference between **Pod**, **Deployment**, and **ReplicaSet**?  
- How does **Kubernetes networking** work (Pod-to-Pod / Service / Ingress)?  
- How does **Service discovery** work in Kubernetes?  
- What is the purpose of **etcd**?  
- How does a **Service (ClusterIP)** route traffic to Pods?  
- What is the difference between **NodePort** and **LoadBalancer**?  
- What’s the role of **kube-proxy**?  
- How does **Ingress** differ from a **Service**?  
- How do you store **persistent data** in Kubernetes?  
- What’s the difference between **ConfigMap** and **Secret**?  
- How do you control **resource usage** (CPU/Memory)?  
- How does **Horizontal Pod Autoscaler (HPA)** work?  
- Explain **Liveness** vs **Readiness** probes.  
- What’s the difference between **ReplicaSet** and **StatefulSet**?  
- How does **RBAC** control permissions?  
- How do **taints and tolerations** work?  
- What are **Namespaces** used for?  
- What are **Admission Webhooks**, and when would you use one?  
- How would you troubleshoot a **Pod stuck in CrashLoopBackOff**?  
- How do you **roll back a deployment** or manage **zero downtime deployments**?

---

### ⚙️ Practical Insights
- **Pod** is the smallest deployable unit — 1+ containers sharing the same network namespace.  
- **Deployment** manages ReplicaSets, ensuring declarative rollout and rollback.  
- **Service** provides stable networking to ephemeral Pods using label selectors.  
- **Ingress** exposes HTTP/HTTPS traffic, often with reverse proxy (Nginx/Traefik).  
- **CoreDNS** provides internal DNS for service discovery (`my-service.my-namespace.svc.cluster.local`).  
- **ConfigMap** stores configuration data (non-sensitive).  
- **Secret** stores sensitive data (Base64-encoded).  
- **PersistentVolume (PV)** represents actual storage; **PVC** claims it for a Pod.  
- **Requests and Limits** control scheduling and prevent resource starvation.  
- **HPA** scales Pods based on metrics (e.g., CPU, custom metrics).  
- **RBAC** defines who (user/service account) can do what (verb) on which resources.  
- **Node scheduling**:
  - `nodeSelector`: simple matching  
  - `affinity/anti-affinity`: expressive constraints  
  - `taints/tolerations`: exclude nodes unless tolerated  
- **Probes:**
  - *Liveness* → restarts container if unhealthy  
  - *Readiness* → removes from service endpoint until ready  
  - *Startup* → gives time for slow apps to boot  
- **Helm** simplifies deployment packaging and versioning.  
- **Operators** extend Kubernetes API using CRDs to automate app lifecycle.  
- **Observability:** always check `kubectl describe pod`, `kubectl logs`, and `kubectl get events` for debugging.  
- **Network model:** every Pod has its own IP; all Pods can reach each other (flat network).  
- **kube-proxy:** manages iptables/IPVS rules for Service load balancing.  

---

### 🚀 Advanced / Extended Topics
- CNI plugins: Flannel, Calico, Cilium, Kube-OVN  
- NetworkPolicy (Ingress/Egress rules)  
- Service Mesh (Istio, Linkerd, Cilium Service Mesh)  
- Pod Security Standards (PSS) / PSP (deprecated)  
- Admission Webhooks for validation & mutation  
- CRDs and Custom Operators  
- Sidecar pattern & init containers  
- Multi-cluster / Federation  
- Autoscaling advanced: HPA + VPA + Cluster Autoscaler  
- Security hardening: least privilege RBAC, restricted PSP/PSS, Secrets encryption at rest  
- Monitoring stack: Prometheus / Grafana / Loki  
- Log aggregation: Fluentd / Loki / Elasticsearch  
- Container runtime evolution: Docker → containerd → CRI-O  
- Troubleshooting networking: `kubectl exec`, `ping`, `traceroute`, `nslookup`, `iptables -t nat -L`

---

### ⚡ Quick Summary
> **Kubernetes orchestrates containerized workloads declaratively.**  
> The **Control Plane** manages state and scheduling; **Nodes** run Pods.  
> **Services** provide stable networking; **Ingress** handles external access.  
> **ConfigMaps/Secrets** manage configuration, **PVC/PV** handle storage.  
> Key to mastery: understand scheduling, probes, and networking.
