# 📌 Project Documentation — React App Deployment with Docker, K3s, and GitHub Actions CI/CD

This project demonstrates how to build, containerize, deploy, and automate a React web application using **Docker**, **K3s Kubernetes**, and **GitHub Actions**.

---

## 1️⃣ Step 1: Build the React Application
- Created a React.js frontend application.
- Installed necessary dependencies.
- Built the production-ready static files.

---

## 2️⃣ Step 2: Dockerize the Application
- Created a Dockerfile to serve the React build via Nginx.
- Built the Docker image locally.
- Verified the container works by running it locally.

---

## 3️⃣ Step 3: Push Image to Docker Hub
- Logged in to Docker Hub from the terminal.
- Tagged the Docker image with Docker Hub username.
- Pushed the image to the Docker Hub repository.

---

## 4️⃣ Step 4: Deploy on Kubernetes (K3s)
- Created a Kubernetes Deployment manifest to run the container in K3s.
- Created a Kubernetes Service manifest to expose the application via NodePort.
- Applied the Kubernetes manifests on the Azure VM running K3s.
- Verified that the application is accessible through `<VM-IP>:<NodePort>`.

---

## 5️⃣ Step 5: Configure Firewall Rules
- Allowed the NodePort in the Azure VM firewall.
- Verified that the app is reachable from outside.

---

## 6️⃣ Step 6: Set Up GitHub Actions (CI/CD)
- Created a GitHub Actions workflow file in `.github/workflows/`.
- Configured the pipeline to:
  1. Checkout the repository.
  2. Build the Docker image.
  3. Push the Docker image to Docker Hub.
  4. SSH into the Azure VM and restart the Kubernetes deployment.
- Added required secrets in GitHub:
  - `DOCKER_USERNAME`
  - `DOCKER_PASSWORD`
  - `VM_IP`
  - `VM_USER`
  - `SSH_KEY`

---

## 7️⃣ Step 7: Test CI/CD Pipeline
- Committed and pushed changes to the main branch.
- Verified that GitHub Actions workflow:
  - Built and pushed the Docker image.
  - Updated the deployment on K3s.
  - Successfully rolled o
