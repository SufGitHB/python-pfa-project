# DevSecOps CI/CD – Python Flask Monitoring App

This is a Python Flask web application providing system information and a real-time monitoring dashboard with CPU, memory, I/O and process metrics.

The app is designed as a cloud-native demo application: simple, lightweight, easy to deploy, and ideal for CI/CD, DevSecOps, containerization, and cloud deployment scenarios such as Azure VM or Kubernetes clusters.

It serves as a practical example for:
- Docker-based deployments
- GitLab CI/CD pipelines (tests → quality → build → deploy)
- SonarCloud static analysis
- Cloud deployments (Azure VM, container platforms)
- DevOps & DevSecOps educational demonstrations

---

## Screenshot

Below is the style-aligned screenshot section with a **working URL**, matching the demo-app template:

![screen](https://user-images.githubusercontent.com/14982936/30533171-db17fccc-9c4f-11e7-8862-eb8c148fedea.png)

> Replace with your real screenshot when ready.

---

# Status

You can adapt these badges to your GitLab and SonarCloud projects:

![](https://img.shields.io/github/last-commit/benc-uk/python-demoapp)  
![](https://img.shields.io/github/release-date/benc-uk/python-demoapp)  
![](https://img.shields.io/github/v/release/benc-uk/python-demoapp)  
![](https://img.shields.io/github/commit-activity/y/benc-uk/python-demoapp)

Live instances (example):

[![](https://img.shields.io/website?label=Hosted%3A%20Azure%20App%20Service&up_message=online&url=https%3A%2F%2Fpython-demoapp.azurewebsites.net%2F)](https://python-demoapp.azurewebsites.net/)  
[![](https://img.shields.io/website?label=Hosted%3A%20Kubernetes&up_message=online&url=https%3A%2F%2Fpython-demoapp.kube.benco.io%2F)](https://python-demoapp.kube.benco.io/)

---

## Building & Running Locally

### Pre-reqs

- Linux, WSL or macOS with bash & make
- [Python 3.9+](https://www.python.org/downloads/) for testing & local execution  
- [Docker](https://docs.docker.com/get-docker/) for container builds and execution  
- [Azure CLI](https://learn.microsoft.com/en-us/cli/azure/install-azure-cli-linux) for deployment to Azure  
- Git + Make installed

Clone the project:

```bash
git clone https://github.com/benc-uk/python-demoapp.git
