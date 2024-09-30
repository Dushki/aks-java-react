# aks-java-react
This repository contains a Java backend and a React frontend application, packaged and deployed using Docker and Kubernetes on an Azure Kubernetes Service (AKS) cluster. This document will guide you through the setup, deployment, and CI/CD pipeline configuration using Azure DevOps.

## Overview

The application consists of two microservices:
Java Backend
React Frontend

Azure Kubernetes Service (AKS) is used to host both the backend and frontend applications.
The backend and frontend services are deployed in separate namespaces (backend-dev and frontend-dev) to maintain logical separation and better resource management.

Containerization
The applications are containerized using Docker. Separate Dockerfile configurations exist for each service under backend folder and frontend folder.

## Deployment Strategy
2 separate pipline are created to deploy backend and frontend -

Run unit test for backend and frontend code
Build Docker images for both frontend and backend.
Push the images to Azure Container Registry (ACR).
Deploy the applications to AKS using Kubernetes manifests (backend-deploy.yaml and frontend-deploy.yaml).

## Troubleshooting

Pods Not Starting: Check the logs using kubectl logs <pod name>

## Future Improvements

Set up Horizontal Pod Autoscaling (HPA) for better scalability.
Implement RBAC for fine-grained access control.
Use Ingress for better routing instead of LoadBalancer services.

