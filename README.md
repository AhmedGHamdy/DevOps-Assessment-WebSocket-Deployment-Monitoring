# DevOps Assessment: WebSocket Deployment & Monitoring

## Overview
Design and implement a **highly available WebSocket service** for streaming stock prices. The service should be **containerized, monitored, secured, and deployed** using modern DevOps practices. Candidates can choose between:
- **Azure App Service** (PaaS)
- **Azure Kubernetes Service (AKS) / On-Prem Kubernetes (RKE2, K3s, or other alternatives)**

The solution should follow **Infrastructure as Code (IaC), GitOps, and security best practices**.

---

## Task Breakdown

### 1. Develop & Containerize the WebSocket Service
- Implement a **Python WebSocket server** to stream stock prices.
- Use **FastAPI / Flask / Django Channels** for WebSocket communication.
- Containerize the application using **Docker** with a production-ready `Dockerfile`.
- Store the image in **Azure Container Registry (ACR) / DockerHub**.

---

### 2. Deploy on Azure (PaaS or Kubernetes)
Candidates must choose one of the following deployment options:

#### **Option 1: Azure App Service**
- Deploy the **containerized WebSocket** using **Azure App Service (Linux Containers)**.
- Configure **scaling rules** based on active WebSocket connections.

#### **Option 2: Kubernetes (AKS, RKE2, K3s, or alternative)**
- Deploy the WebSocket container on Kubernetes.
- Implement **Horizontal Pod Autoscaler (HPA)** for scaling WebSocket pods.
- Use **Ingress (NGINX/Traefik)** for external access.

---

### 3. Implement GitOps & CI/CD (GitHub Actions + ArgoCD)
- **GitHub Actions Pipeline** should:
  - Build and push the Docker image to **ACR/DockerHub**.
  - Deploy the app using **Terraform (for infrastructure)** and **Helm (for Kubernetes)**.
  - Use **ArgoCD** for GitOps-based deployment on AKS.

- **For Azure App Service:**
  - Use **Terraform to provision App Service & ACR**.
  - GitHub Actions should deploy the WebSocket container on commit.

---

### 4. Implement Monitoring & Alerting
- **Prometheus & Blackbox Exporter**:
  - Deploy **Blackbox Exporter** to probe WebSocket availability via TCP.
  - Configure **Prometheus** to scrape Blackbox metrics.
  - Monitor **latency, uptime, and failures**.
- **Azure Monitor (For App Service):**
  - Enable **Azure Monitor** for application performance tracking.
  - Create alerts for **latency spikes, WebSocket failures, and downtime**.
- **Grafana Dashboard**:
  - Visualize WebSocket health and performance.

---

### 5. Implement Auto-Healing & High Availability
- **Azure App Service**:
  - Configure auto-restart on failure.
  - Enable **Auto-Scaling** based on active connections.
- **Kubernetes (AKS, RKE2, etc.)**:
  - Use **Liveness & Readiness Probes** to restart failing pods.
  - Deploy with **Multiple Replicas** for fault tolerance.
- **Self-Healing via Monitoring**:
  - Create **Prometheus AlertManager rules** to restart WebSocket instances on failure.
  - Implement **Azure Functions / Kubernetes Jobs** to trigger restarts.

---

### 6. Security & Compliance
- **Container Security**:
  - Scan images using **Trivy / Aqua Security** before deployment.
  - Restrict access to only necessary ports.
- **Network Security**:
  - Use **Azure Private Link / NSGs** to secure WebSocket communication.
- **Authentication & Authorization**:
  - Secure WebSocket connections using **JWT/OAuth (Azure AD, Keycloak, Firebase, etc.)**.
- **Secrets Management**:
  - Store secrets in **Azure Key Vault / Kubernetes Secrets**.

---

### 7. Documentation & Submission
Candidates must submit:
✅ **Architecture Diagram** (showing all components).
✅ **Terraform / Helm Charts** for infrastructure and deployment.
✅ **CI/CD Pipeline Code** (GitHub Actions).
✅ **Prometheus/Grafana setup** with screenshots.
✅ **README** explaining setup & deployment instructions.

---

### Bonus (Optional Enhancements)
🔥 **Redis / Azure Service Bus for WebSocket Load Balancing**
🔥 **WebSocket Message Queuing for High Availability**
🔥 **Istio / Linkerd for Service Mesh & Traffic Management**



### Expected Deliverables
- **GitHub Repository** with all IaC, app code, and pipelines.
- **Deployed WebSocket on Azure (App Service or AKS).**
- **Live Monitoring Dashboard (Grafana)** showing real-time data.
- **Prometheus alerts triggering automatic recovery.**

---

## Final Notes
This assessment tests **end-to-end DevOps skills**, including **Kubernetes, CI/CD, monitoring, auto-scaling, and security**. Candidates can choose their preferred **orchestration method (Azure App Service or Kubernetes)**.

---

### Need Assistance?
If you have any questions, feel free to ask! 🚀
