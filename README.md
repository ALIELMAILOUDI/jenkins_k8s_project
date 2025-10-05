# CI/CD Pipeline for Spring Boot + MongoDB Application using Jenkins, Docker, and Minikube

## Project Description

This project demonstrates the implementation of a **complete CI/CD pipeline** for a **Spring Boot and MongoDB** application using **Jenkins**, **Docker**, and **Kubernetes (Minikube)**.

The main objective is to automate the software delivery process — from code integration to deployment — ensuring that every code change is automatically built, tested, scanned for security vulnerabilities, containerized, and deployed to a local Kubernetes cluster.

This setup follows the **DevOps principles** of Continuous Integration (CI) and Continuous Deployment (CD), providing a reproducible, secure, and automated workflow.

---

## Architecture Overview

The following diagram illustrates the architecture and workflow of the CI/CD pipeline:

<img width="1168" height="651" alt="image" src="https://github.com/user-attachments/assets/f7002073-86b1-4b3c-83a1-f842483b1c74" />


---

## Workflow Summary

1. **Code Commit (GitHub)**  
   The source code of the Spring Boot + MongoDB application is hosted on GitHub.

2. **Jenkins Pipeline**  
   Jenkins automatically pulls the latest code from GitHub and executes the defined pipeline stages:
   - **Maven Build:** Compile and package the application.
   - **OWASP Dependency Check:** Detect known vulnerabilities in dependencies.
   - **SonarQube Analysis:** Analyze code quality and generate metrics.
   - **Docker Build:** Containerize the application into a Docker image.
   - **Trivy Scan:** Scan the image for security vulnerabilities.
   - **Docker Push:** Push the image to Docker Hub.
   - **Kubernetes Deployment:** Deploy the application on Minikube.

3. **Minikube (Kubernetes)**  
   The containerized application is deployed on a local Kubernetes cluster (Minikube).  
   Jenkins connects securely to Minikube using Kubernetes credentials.

4. **Monitoring & Verification**  
   Once deployed, you can verify the running application using `kubectl` commands and access the service via Minikube’s exposed URL.

---
