# DevSecOps CI/CD – Python Flask Monitoring App

This repository contains the source code and DevSecOps toolchain for a Python Flask web application that exposes real‑time system monitoring (CPU, memory, processes, etc.) via a web dashboard.[web:29][web:31]  
The goal of this project is not only to deliver an application, but to implement a complete, production‑style CI/CD pipeline with quality analysis, containerization, and automated deployment to Azure.

Typical uses of this project include demonstrations of DevOps/DevSecOps practices, GitLab CI/CD pipelines, Docker image build and delivery, SonarCloud static analysis, and automated deployment to a Linux virtual machine on Microsoft Azure.[web:26][web:11]

---

## Project overview

This project is part of a PFA/PFE focused on:

- Designing and packaging a Flask monitoring application in a reproducible way with Docker.[web:26]  
- Implementing a GitLab CI/CD pipeline covering tests, quality gates, image build, and deployment stages.  
- Integrating SonarCloud for code quality, coverage, and security analysis of the Python codebase.[web:9][web:18]  
- Deploying the resulting container on an Azure Linux virtual machine and exposing the application over HTTP.[web:11][web:14]

The repository also includes documentation, Makefile helpers, and infrastructure scripts to make local development, testing, and deployment repeatable for any contributor.

---

## Architecture

At a high level, the solution is composed of:

- **Application layer**  
  - Python Flask web app exposing a dashboard with system metrics (CPU, memory, running processes, etc.).[web:26][web:29]  
  - REST/JSON endpoints consumed by the frontend for periodic refresh.

- **DevOps / CI/CD layer**  
  - `.gitlab-ci.yml` pipeline with stages: `test` → `sonarqube` → `build` → `deploy`.  
  - SonarCloud integration for static code analysis, coverage reporting, and quality gates.[web:9][web:18]  
  - Docker image build and push to a container registry (GitLab Container Registry or Docker Hub).

- **Runtime / Infra layer**  
  - Azure Linux VM hosting Docker and running the application container on port 5000.[web:11][web:14]  
  - Optional support for Kubernetes or other container platforms if needed.

---

## Screenshot

A typical runtime dashboard shows running processes and real‑time CPU and memory gauges:

![screen](./docs/images/dashboard-example.png)

> Update the image path above (`./docs/images/dashboard-example.png`) with the actual location of your screenshot in this repository.

---

## Status

Example status badges (adapt to your GitLab project and SonarCloud project):

- GitLab pipeline:  
  `![GitLab pipeline status](https://gitlab.com/<group>/<project>/badges/main/pipeline.svg)`
- SonarCloud quality gate:  
  `![Quality Gate Status](https://sonarcloud.io/api/project_badges/measure?project=<sonar-project-key>&metric=alert_status)`

Live instances (if applicable):

- Azure VM: `http://<public-ip>:5000`
- Other environments (staging, Kubernetes, etc.) can be added here.

---

## Tech stack

- **Backend:** Python 3.9+, Flask micro‑framework.[web:26]  
- **Monitoring libs:** `psutil` for system metrics.  
- **Packaging:** Docker, Dockerfile in repository root.  
- **CI/CD:** GitLab CI/CD with `.gitlab-ci.yml`.  
- **Quality & Security:** SonarCloud (bugs, vulnerabilities, code smells, coverage, duplications).[web:9][web:18]  
- **Cloud:** Microsoft Azure Linux VM for deployment.[web:11][web:14]

---

## Building & running locally

### Prerequisites

- Linux, WSL ou macOS avec `bash`, `make`, `git`.  
- Python 3.9+ installé (utilisation locale, linting, tests).[web:26]  
- Docker pour le build et l’exécution en conteneur.[web:11]  
- Azure CLI (pour interactions et déploiement vers Azure VM si nécessaire).[web:11][web:14]  
- Accès à votre projet GitLab (SSH ou HTTPS).

### Cloner le projet

