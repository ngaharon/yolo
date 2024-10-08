# Overview
This project involved the containerization and deployment of a full-stack yolo application using Docker.


# Requirements
Install the docker engine here:
- [Docker](https://docs.docker.com/engine/install/) 

## How to launch the application 
### Method 1 (faster)
- NOTE: This method does not require cloning of this repository

- Navigate to the launch_app folder and copy the contents of the [docker-compose.yaml] in the root of the project
- On your local machine, navigate to your desired directory and create
  a docker-compose.yaml file, paste the contents into it and save

  `touch docker-compose.yaml`

- Launch the application using docker compose up

  `docker compose up`

### Method 2
- NOTE: This requires cloning of this whole repository

- Clone this repository to your local machine

  `git clone https://github.com/ngaharon/yolo.git`

- Navigate to the root directory of your cloned repository

  `cd yolo`

- Launch the application using the docker compose command

  `docker compose up`

## Access the application on your browser using the following URL
 `http://localhost:3000/`

## How to stop the application
- Navigate back to your terminal and press "ctrl+c" 

## How to terminate the application completely
 `docker compose down`

## The Docker images used in this application are sourced from this repository

https://hub.docker.com/repositories/harondevops6

![Alt text](image.png)

## How to run the app
Use vagrant up --provison command

### prerequisites

- Kubernetes cluster (e.g., GKE, EKS, or Minikube)
- kubectl configured to use your cluster
- Docker Hub account
 
 ## Deployment
 1. Clone this repository
 2. Apply the Kubernetes manifests: `kubectl apply -f ...`
 3. Wait for all pods to be in the "Running" state: `kubectl get pods --watch`
 4. Access the application: 4. Access the application: `kubectl get services client-service`

 Use the EXTERNAL-IP and port 80 to access the application in your browser.

## Architecture

- client: React application
- Backend: Node.js API
- Database: MongoDB

## Troubleshooting

If you encounter issues, check the pod logs: `kubectl logs <pod-name>`


