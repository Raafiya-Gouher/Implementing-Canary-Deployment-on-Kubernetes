# Implementing-Canary-Deployment-on-Kubernetes
# Kubernetes Canary Deployment of Django App with Monitoring  
_Minikube + NGINX Ingress + Prometheus + Grafana_  

## 1. Project Overview

This project deploys a Python Django sample app to a **local Kubernetes cluster (Minikube)** and implements:

- **Stable + Canary deployments** of the app  
- **ClusterIP Services** for traffic routing  
- **NGINX Ingress** with **host-based & path-based routing**  
- **Canary release** using NGINX Ingress canary annotations  
- **Monitoring stack** using **Prometheus + Grafana (kube-prometheus-stack)**  
- Access to **Grafana UI** on `http://localhost:3000`  

Key values used:

- Stable app image: `raafiyagouher/python-sample-app:1.0.0`  
- Canary app image: `raafiyagouher/python-sample-app:1.1.0`  
- App host: `python-web.local`  
- App path: `/demo`  
- App namespace: `python-web`  
- Monitoring namespace: `monitoring`  

---

## 2. Prerequisites

- Windows 10 Pro (with Hyper-V capability)
- PowerShell (Run as Administrator for some steps)
- Internet connection
- [Optional] Helm 3 installed (for Prometheus/Grafana)

### 2.1 Enable Hyper-V

```powershell
Enable-WindowsOptionalFeature -Online -FeatureName Microsoft-Hyper-V -All
Reboot after this.
