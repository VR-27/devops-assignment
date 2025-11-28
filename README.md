# MEAN Stack DevOps Deployment

A full-stack MEAN application (MongoDB, Express, Angular, Node.js) containerized with Docker and deployed to AWS EC2 using a CI/CD pipeline.

## 🚀 Tech Stack
* **Frontend:** Angular (Served via Nginx Reverse Proxy)
* **Backend:** Node.js & Express
* **Database:** MongoDB (Docker Container)
* **DevOps:** Docker, GitHub Actions, AWS EC2

## 🛠️ Setup & Deployment

### 1. Prerequisites
* An AWS EC2 instance (Ubuntu) with Ports `80` (HTTP) and `22` (SSH) open.
* Docker and Docker Compose installed on the VM.
* A Docker Hub account.

### 2. Repository Setup
* Create a Github Repository
* Add the Project

### 3. CI/CD Configuration
* The pipeline (.github/workflows/deploy.yml) automates the following:
* Builds and Pushes Docker images to Docker Hub.
* Connects to AWS EC2 via SSH.
* Pulls new images and restarts containers.

### 4. Nginx Reverse Proxy
* Nginx is configured to serve the application entirely on Port 80:
* /: Serves the Angular Frontend.
* /api: Proxies requests internally to the Node.js Backend
