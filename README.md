# Capstone Project - Containerization and Container Orchestration

## Project Overview

This project involves creating a simple static website and deploying it using Docker and Kubernetes. The primary goal is to containerize a frontend application, push it to Docker Hub, and deploy it to a Kubernetes cluster managed by Kind (Kubernetes in Docker).

## Phase 1: Basic Frontend Application with Docker and Kubernetes

## Tasks Overview

### Task 1: Set up the Project
1. Create a new project directory.
2. Inside the directory, add the following files:
   - `index.html` (HTML file for the website)
   - `styles.css` (CSS file for styling)

### Task 2: Initialize Git
- Initialize a Git repository in the project directory.

### Task 3: Commit Initial Code
- Add and commit your code to the Git repository.

### Task 4: Dockerize the Application
1. Create a `Dockerfile` using Nginx as the base image.
2. Copy the `index.html` and `styles.css` files into the Nginx HTML directory.

### Task 5: Push to Docker Hub
1. Log in to Docker Hub.
2. Push the Docker image to your Docker Hub repository.

### Task 6: Set Up a Kind Kubernetes Cluster
1. Install Kind (Kubernetes in Docker).
2. Create a Kind cluster.

### Task 7: Deploy to Kubernetes
1. Create a Kubernetes Deployment YAML file to specify:
   - The Docker image
   - Desired replicas
2. Apply the deployment to the Kind cluster.

### Task 8: Create a Service (ClusterIP)
1. Create a Kubernetes Service YAML file specifying the service type as `ClusterIP`.
2. Apply the service to your cluster.

### Task 9: Access the Application
1. Port-forward the service to access the application locally.
2. Open your browser and navigate to the forwarded port to view the application.

---

## Project Files
The following files will be included in the project:
- `index.html` (Frontend HTML content)
- `styles.css` (CSS styling)
- `Dockerfile` (To containerize the application using Nginx)
- `my-nginx-deployment.yaml` (Kubernetes Deployment configuration)
- `my-nginx-service.yaml` (Kubernetes Service configuration)

---

## How to Run the Project

### Prerequisites
- Docker installed on your system
- Kubernetes tools (e.g., `kubectl` and Kind)
- Docker Hub account

### Steps
1. Clone this repository.
2. Build the Docker image:
   ```bash
   docker build -t <your-dockerhub-username>/<repository-name>:<tag> .
   ```
3. Push the Docker image to Docker Hub:
   ```bash
   docker push <your-dockerhub-username>/<repository-name>:<tag>
   ```
4. Create a Kind cluster:
   ```bash
   kind create cluster
   ```
5. Deploy the application:
   ```bash
   kubectl apply -f deployment.yaml
   kubectl apply -f service.yaml
   ```
6. Access the application:
   ```bash
   kubectl port-forward svc/<service-name> <local-port>:<service-port>
   ```
   Open your browser and navigate to `http://localhost:<local-port>`.

---

## Acknowledgments
This project is part of a containerization and orchestration capstone. Special thanks to mentors and peers for their guidance.
