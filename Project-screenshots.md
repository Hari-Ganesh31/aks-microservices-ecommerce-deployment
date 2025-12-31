# 📸 Deployment Walkthrough – AKS Microservices Project

This document contains step-by-step screenshots explaining how I deployed the 
multi-microservice e-commerce application (Instana Robot Shop) on Azure Kubernetes Service (AKS).

---

## 1️⃣ AKS Cluster Created Successfully

![rec-k8s](https://github.com/user-attachments/assets/570982e9-d411-48c9-adf6-c797d1ffb170)

![rec-11](https://github.com/user-attachments/assets/f605f334-1a4e-4eed-b852-3411e66168d5)

I created an Azure Kubernetes Service (AKS) cluster with appropriate VM size and node count.
This cluster acts as the control environment where Kubernetes manages worker nodes and pods.

---

## 2️⃣ Node Pool Configuration

![node-pool](https://github.com/user-attachments/assets/8b76fd6c-90bb-4f90-8217-3e074ec3015b)


After cluster creation, a node pool was configured. 
This defines the virtual machines where pods run. 
I ensured the correct vCPU capacity so that microservices could schedule without **Insufficient CPU** errors.

---

## 3️⃣ Pods Running in Kubernetes

![Pods Running](screenshots/pods-running.png)

Here you can see multiple microservice pods in **Running** state.
Each pod represents a container instance running part of the e-commerce application.

Earlier some pods were pending due to CPU limitations — those were resolved by adjusting node size.

---

## 4️⃣ Kubernetes Services

![Services](screenshots/services.png)

Services were deployed automatically using Helm charts.
They provide stable networking inside the cluster and expose internal/external endpoints.

---

## 5️⃣ Helm Chart Deployment

![Helm List](screenshots/helm-list.png)

The application was deployed using Helm.
Helm simplifies application deployment by packaging Kubernetes manifests into reusable charts.

---

## 6️⃣ Ingress Controller Configuration

![Ingress](screenshots/ingress.png)

Azure Application Gateway Ingress Controller was used to route external traffic to services.
It provides:

- single entry point
- clean domain-based routing
- SSL readiness
- load balancing

---

## 7️⃣ Application Running in Browser

![Application UI](screenshots/app-ui.png)

This screenshot shows the e-commerce application successfully accessible from a browser through the ingress endpoint.
All backend microservices work together to serve this UI.

---

## 📝 Notes

- Application source code belongs to **Instana Robot Shop**
- I used the existing Helm charts and Kubernetes YAML provided in project
- My focus was on **deployment & troubleshooting on AKS**

---

## 🎬 Demo Video

👉 Watch deployment demonstration video here:  
`<paste your YouTube or Drive link here>`
