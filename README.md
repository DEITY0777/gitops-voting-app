# Voting App CI/CD(Jenkins + K8S + ArgoCD)

A complete end-to-end DevOps implementation demonstrating Kubernetes cluster setup using Kind on AWS EC2, GitOps-based deployment with Argo CD, automated CI/CD pipelines using Jenkins, container image security scanning with Trivy, and deployment of an auto-scalable (HPA-enabled) application with full observability using Prometheus and Grafana.


* A front-end web app in [Python](/vote) which lets you vote between two options
* A [Redis](https://hub.docker.com/_/redis/) which collects new votes
* A [.NET](/worker/) worker which consumes votes and stores them in…
* A [Postgres](https://hub.docker.com/_/postgres/) database backed by a Docker volume
* A [Node.js](/result) web app which shows the results of the voting in real time

# Tech Stack

- AWS EC2

- Docker

- Kubernetes

- Jenkins (CI/CD)

- Trivy

- Argo CD (GitOps)

- Prometheus

- Grafana

# Setup Instructions:

- Launch EC2

- Install Docker

- Install Kind

- Create cluster

- Install Argo CD

- Install metrics-server

- Install kube-prometheus-stack

- Access dashboards

# CI/CD Architecture

This project implements a modular CI/CD pipeline using Jenkins 

<img width="1331" height="491" alt="image" src="https://github.com/user-attachments/assets/a76822e5-a4de-4f4b-8f01-670723993c8a" />


- Continuous Integration (CI)

Builds custom Docker image for result service

Performs container image vulnerability scan using Trivy

Pushes image to DockerHub

Automatically triggers CD pipeline

- Continuous Delivery (CD)

Pulls updated image tag from CI

Updates Kubernetes manifest (result-deployment.yaml)

Commits and pushes changes back to GitHub

Argo CD automatically syncs and deploys updated image (GitOps flow)

# Security Practices Implemented

- Trivy image vulnerability scanning

- Docker credential handling via Jenkins credentials

- SSH-based GitHub authentication

- Resource limits defined in Kubernetes manifests

- HPA for controlled scaling

# ArgoCD Flow

High Load:
<img width="1917" height="918" alt="Argocd" src="https://github.com/user-attachments/assets/12837e9f-d41a-4d10-86d7-c1d40945cdc5" />

Normal Load:
<img width="1911" height="917" alt="image" src="https://github.com/user-attachments/assets/a75c5165-40fd-4d61-8f7d-c7e1432bb97e" />


# Observability
<img width="1893" height="916" alt="grafana dashboard" src="https://github.com/user-attachments/assets/d65c3747-75ef-4fb9-820f-a4ec1d6a6921" />

<img width="1567" height="554" alt="image" src="https://github.com/user-attachments/assets/14a4be2e-6520-4549-ab79-40514d25b8b7" />


Guidance From:

- trainwithshubham

