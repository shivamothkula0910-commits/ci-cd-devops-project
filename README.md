# CI/CD DevOps Project

## Overview
This project demonstrates an end-to-end CI/CD pipeline using Flask, Docker, Kubernetes, and GitHub Actions.

## Architecture
GitHub -> GitHub Actions -> Docker Build -> Docker Hub -> Kubernetes Deployment

## Tech Stack
- Python Flask
- Docker
- Kubernetes
- GitHub Actions
- Docker Hub
- Minikube

## Features
- Automated testing with pytest
- Docker image build and push
- Kubernetes deployment with health checks
- CI/CD pipeline triggered on every push to main

## Project Structure
- `app/` - application source code
- `k8s/` - Kubernetes manifests
- `.github/workflows/` - CI/CD pipeline
- `Dockerfile` - container build instructions

## How to Run Locally

```bash
python -m venv venv
source venv/bin/activate
pip install -r app/requirements.txt
pytest app/test_app.py
docker build -t ci-cd-devops-project .
docker run -p 5000:5000 ci-cd-devops-project
```

## How to Deploy to Kubernetes

```bash
minikube start
kubectl apply -f k8s/deployment.yaml
kubectl apply -f k8s/service.yaml
minikube service flask-devops-service
```

## CI/CD Workflow
On every push to the `main` branch:
1. Install dependencies
2. Run tests
3. Build Docker image
4. Push image to Docker Hub

## Results
- Automated application validation
- Faster and repeatable deployments
- Production-style Kubernetes deployment with probes

## Important Update
Before deploying to Kubernetes, replace this placeholder in `k8s/deployment.yaml`:

`YOUR_DOCKERHUB_USERNAME`

with your actual Docker Hub username.
