# DevSecOps CI/CD – Python Flask Monitoring App

This is a Python Flask web application providing system information and a real-time monitoring dashboard with CPU, memory, I/O and process metrics.

The app is designed as a cloud-native demo application: simple, lightweight, easy to deploy, and ideal for CI/CD, DevSecOps, containerization, and cloud deployment scenarios such as Azure VM or Kubernetes clusters.

It serves as a practical example for:
- Docker-based deployments  
- GitLab CI/CD pipelines (tests → quality → build → deploy)  
- SonarCloud static analysis  
- Cloud deployments (Azure VM + Docker)  
- DevOps & DevSecOps educational demonstrations  

---

## Screenshot

![screen](https://user-images.githubusercontent.com/14982936/30533171-db17fccc-9c4f-11e7-8862-eb8c148fedea.png)

> Replace with your real screenshot when ready.

---

# Status

### 🔄 GitLab CI/CD Pipeline
![Pipeline](https://gitlab.com/soufiane.mailinfo/python-pfa-project/badges/main/pipeline.svg)

### 🛡️ SonarCloud Quality Gate
![Quality Gate](https://sonarcloud.io/api/project_badges/measure?project=soufiane-mailinfo_python-pfa-project&metric=alert_status)

### 🌐 Live Deployment (Azure VM)
This project is deployed on an **Azure Linux Virtual Machine** using Docker.

Access the application (after deployment):

👉 **http://<YOUR-AZURE-PUBLIC-IP>:5000**

Replace `<YOUR-AZURE-PUBLIC-IP>` with the real IP of your VM.

---

## Building & Running Locally

### Pre-reqs

- Linux, WSL or macOS with bash & make  
- [Python 3.9+](https://www.python.org/downloads/)  
- [Docker](https://docs.docker.com/get-docker/)  
- [Azure CLI](https://learn.microsoft.com/en-us/cli/azure/install-azure-cli-linux)  
- Git + Make installed  

Clone the project:

```bash
git clone https://gitlab.com/soufiane.mailinfo/python-pfa-project.git
