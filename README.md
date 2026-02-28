# K8s Kind Voting App

A comprehensive guide for setting up a Kubernetes cluster using Kind on an AWS EC2 instance, installing and configuring Argo CD, and deploying application using Argo CD.


* A front-end web app in [Python](/vote) which lets you vote between two options
* A [Redis](https://hub.docker.com/_/redis/) which collects new votes
* A [.NET](/worker/) worker which consumes votes and stores them in…
* A [Postgres](https://hub.docker.com/_/postgres/) database backed by a Docker volume
* A [Node.js](/result) web app which shows the results of the voting in real time

# ArgoCD Flow
<img width="1917" height="918" alt="Argocd" src="https://github.com/user-attachments/assets/12837e9f-d41a-4d10-86d7-c1d40945cdc5" />


# Observability
<img width="1893" height="916" alt="grafana dashboard" src="https://github.com/user-attachments/assets/d65c3747-75ef-4fb9-820f-a4ec1d6a6921" />

<img width="1567" height="554" alt="image" src="https://github.com/user-attachments/assets/14a4be2e-6520-4549-ab79-40514d25b8b7" />


Guidance From:

- trainwithshubham

