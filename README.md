# DevSecOps CI/CD – Python Flask Monitoring App

This repository contains the source code and DevSecOps toolchain for a Python Flask web application exposing real-time system metrics (CPU, memory, processes, etc.) through a modern dashboard.

The goal of this project is not only to ship an application, but to implement a complete production-style CI/CD pipeline with testing, quality analysis, containerization, and automated deployment to Microsoft Azure.

Typical use cases include DevOps/DevSecOps workshops, GitLab CI/CD demonstrations, Docker image builds, SonarCloud analysis, and automated deployment to a Linux virtual machine.

---

## 🚀 Project Overview

This project is part of a PFA/PFE focused on:

- Designing and packaging a Flask monitoring app in a reproducible Docker container  
- Implementing a GitLab CI/CD pipeline with stages:  
  `test → quality → build → deploy`
- Integrating SonarCloud for code quality, coverage, and security analysis  
- Deploying the container on Azure VM (port 5000 exposed)

The repository also includes documentation, Makefile commands, and deployment scripts to ensure repeatability.

---

## 🧱 Architecture

### **Application Layer**
- Python Flask app exposing system metrics:
  - CPU usage
  - Memory usage
  - Running processes
- REST/JSON endpoints used by the frontend for auto-refresh

### **DevOps / CI/CD Layer**
- `.gitlab-ci.yml` defining:
  - Test stage (pytest + coverage)
  - SonarCloud analysis
  - Docker build & push
  - Automated remote deployment (SSH + Docker Run)
- Quality gates enforced through SonarCloud
- Docker image published to a container registry (Docker Hub / GitLab Registry)

### **Runtime / Infra Layer**
- Azure Linux VM running Docker
- Application published on port `5000`
- Optional compatibility with Kubernetes or container platforms

---

## 📸 Screenshot

Here is the dashboard screenshot of the application (real-time CPU/memory gauges + process list):

![Application Dashboard](./docs/images/dashboard-example.png)

> Make sure the image exists under: `docs/images/dashboard-example.png`

---

## 🔖 Status Badges (Example)

Adapt these to match your GitLab project and SonarCloud configuration:

**GitLab pipeline**
