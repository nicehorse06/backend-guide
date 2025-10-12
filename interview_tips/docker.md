## 🐳 Docker

### 🧩 Keywords
- Docker Engine / Docker Daemon / Docker CLI  
- **Image vs Container**  
- UnionFS / OverlayFS  
- Container runtime (containerd, runc)  
- **Namespaces** (PID, NET, IPC, MNT, UTS)  
- **cgroups** (resource limits for CPU, memory, I/O)  
- Dockerfile / Build context / Layers / Caching  
- Docker Registry / Docker Hub / Private registry  
- **Docker Compose** / `docker-compose.yml`  
- Networking modes: bridge, host, none, overlay  
- Volumes / Bind mounts / tmpfs  
- EntryPoint vs CMD  
- Multi-stage builds  
- OCI (Open Container Initiative) standard  

---

### 💬 Common Interview Questions
- What’s the difference between a **Docker image** and a **Docker container**?  
- How does a **container** differ from a **virtual machine (VM)**?  
- Explain how Docker **isolates processes** on Linux.  
- What are **namespaces** and **cgroups**?  
- How does Docker achieve **lightweight virtualization**?  
- What is the purpose of a **Dockerfile**?  
- Explain Docker **layer caching** and how it improves build performance.  
- How does **Docker Compose** help in local development?  
- What is the **difference between ENTRYPOINT and CMD**?  
- How do you **persist data** in a container?  
- How does **Docker networking** work (bridge vs host vs overlay)?  
- How do you **debug a failed build** or a **crashing container**?  
- How would you **reduce image size** or improve build speed?  

---

### ⚙️ Practical Insights
- **Image vs Container:**
  - Image = blueprint (read-only layers)
  - Container = running instance (adds writable layer on top)
- **Container vs VM:**
  - Containers share the **host OS kernel**, while VMs emulate hardware and run their own OS → containers are faster, smaller, but less isolated.
- **Namespaces:** isolate *what a process can see* (PID, network, filesystem).  
- **cgroups:** limit *what a process can use* (CPU, memory, I/O).  
- **UnionFS / OverlayFS:** combines multiple read-only layers + one writable layer.  
- **Docker Compose:** defines multi-container setups with services, volumes, and networks.  
- Use **multi-stage builds** to drastically shrink production image size.  
- Keep images lean: start from `alpine` or `distroless`.  
- Always pin base image versions (`python:3.12-slim`) to ensure reproducibility.  
- Use `.dockerignore` to exclude unnecessary files from build context.  
- **Volume mounts** for persistent data; avoid storing state inside containers.  
- Docker networking:
  - `bridge`: default, NAT-based, isolated per host  
  - `host`: shares host network namespace (better performance, less isolation)  
  - `overlay`: for multi-host (Swarm / Kubernetes)  
- Avoid running containers as root; use `USER` directive in Dockerfile.  

---

### 🚀 Advanced / Extended Topics
- Difference between **Docker** and **containerd / Podman / CRI-O**  
- How Kubernetes uses Docker (historically via dockershim, now via containerd)  
- OCI standards: Image Spec, Runtime Spec  
- Container startup process: `docker run` → create namespace → mount layers → execute process  
- Security hardening: seccomp profiles, capabilities, AppArmor  
- Performance tuning: overlay2 vs devicemapper drivers  
- Registry optimizations: image signing, caching proxies, scanning (Trivy, Clair)  
- Multi-architecture images (ARM vs x86)  

---

### ⚡ Quick Summary
> **Docker isolates processes using Linux namespaces and cgroups.**  
> An **image** is a read-only template; a **container** is a running instance with its own writable layer.  
> Containers share the host OS kernel (unlike VMs).  
> **Docker Compose** orchestrates multi-container setups.  
> Focus on build caching, small base images, and secure configurations.
