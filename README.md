# DevSecOps CI/CD – Python Flask Monitoring App

This is a Python Flask web application providing system information and a real-time monitoring dashboard with CPU, memory, I/O and process metrics.

The app is designed as a cloud-native demo application: simple, lightweight, easy to deploy, and ideal for CI/CD, DevSecOps, containerization, and cloud deployment scenarios such as Azure VM or Kubernetes clusters.

It serves as a practical example for:
- Docker-based deployments  
- GitHub Actions CI/CD pipeline (tests → quality → build → deploy)  
- SonarCloud static analysis  
- Cloud deployments (Azure VM + Docker)  
- DevOps & DevSecOps educational demonstrations  

---

## Screenshot

![screen](https://user-images.githubusercontent.com/14982936/30533171-db17fccc-9c4f-11e7-8862-eb8c148fedea.png)

> Replace with your real screenshot when ready.

---

# Status

### 🔄 GitHub Actions CI/CD Pipeline
[![CI/CD](https://github.com/SufGitHB/python-pfa-project/actions/workflows/ci-cd.yaml/badge.svg?branch=main)](https://github.com/SufGitHB/python-pfa-project/actions/workflows/ci-cd.yaml)

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
git clone https://github.com/SufGitHB/python-pfa-project.git
cd python-pfa-project
```

Run locally:

```bash
make run        # http://localhost:5000
make test       # unit tests
make lint       # black + flake8
```

---

## CI/CD (GitHub Actions)

The pipeline is defined in [`.github/workflows/ci-cd.yaml`](.github/workflows/ci-cd.yaml):

| Stage | Runs on | What it does |
|-------|---------|--------------|
| `test` | push / PR | pytest with coverage report |
| `sonarcloud` | push / PR | SonarCloud analysis using the coverage report |
| `build` | push to `main` | Builds and pushes `soufiane474/pfa-project` to Docker Hub |
| `deploy` | push to `main` | Restarts the container on the Azure VM over SSH and checks the site responds |

Repository secrets required (*Settings → Secrets and variables → Actions*):

| Secret | Purpose |
|--------|---------|
| `SONAR_TOKEN`, `SONAR_ORG`, `SONAR_PROJECT_KEY`, `SONAR_PROJECT_NAME` | SonarCloud |
| `DOCKER_USER`, `REGISTRY_PASS` | Docker Hub login |
| `SSH_PASSWORD` | SSH login to the Azure VM (`azureuser`) |

Optional repository variable: `DEPLOY_HOST` to override the Azure VM IP.
