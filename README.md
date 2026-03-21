# 🚀 CI Pipeline using GitHub Actions (Spring Boot + Self-Hosted Runner)

## 📌 Project Overview

This project demonstrates a complete **CI (Continuous Integration) pipeline** using **GitHub Actions** with a **self-hosted Ubuntu runner** for a Spring Boot application.

The pipeline automates the process of building, testing, scanning, and packaging the application into a Docker image.

---

## ⚙️ Technologies Used

* GitHub Actions (CI Tool)
* Self-Hosted Ubuntu Runner
* Java (Spring Boot)
* Maven (Build Tool)
* SonarQube (Code Quality & Security Scan)
* Snyk (Dependency Vulnerability Scan)
* Docker (Containerization)
* Docker Hub (Image Registry)

---

## 🔄 CI Pipeline Workflow

The pipeline is divided into multiple jobs:

### 1️⃣ Code Checkout

* The pipeline starts by pulling the source code from the GitHub repository.

### 2️⃣ Build Stage (Maven)

* The application is built using Maven.
* Ensures code compiles successfully.

### 3️⃣ Code Quality & Security Scan (SonarQube)

* Static code analysis is performed.
* Detects bugs, vulnerabilities, and code smells.

### 4️⃣ Dependency Vulnerability Scan (Snyk)

* Scans project dependencies.
* Identifies known vulnerabilities in libraries.

### 5️⃣ Docker Build & Push

* Docker image is built for the Spring Boot application.
* Image is pushed to Docker Hub.
* Credentials are securely managed using GitHub Secrets.

---

## 🔐 Secrets Management

Sensitive data like Docker Hub credentials are stored securely using **GitHub Secrets**.

Example:

* `DOCKER_USERNAME`
* `DOCKER_PASSWORD`

This ensures credentials are not exposed in the pipeline.

---

## 🖥️ Self-Hosted Runner

Instead of using GitHub-hosted runners, this project uses a **self-hosted Ubuntu runner**.

### Advantages:

* Full control over environment
* Better performance for heavy builds
* Custom tools and configurations

---

## 🔍 GitHub Actions vs Jenkins

| Feature     | GitHub Actions                            | Jenkins                             |
| ----------- | ----------------------------------------- | ----------------------------------- |
| Setup       | Easy (integrated with GitHub)             | Complex setup & maintenance         |
| Maintenance | No server management (unless self-hosted) | Requires server & plugin management |
| Integration | Native GitHub integration                 | Requires plugins                    |
| Scalability | Automatically scalable                    | Manual scaling required             |
| UI/UX       | Modern and simple                         | Older UI                            |
| Cost        | Free tier available                       | Requires infrastructure             |

---

## 🤔 Why People Prefer GitHub Actions over Jenkins

1. **Tight Integration with GitHub**

   * Directly works with repositories, pull requests, and commits.

2. **No Maintenance Overhead**

   * No need to manage Jenkins servers and plugins.

3. **Simpler Configuration**

   * YAML-based workflows are easy to understand and maintain.

4. **Scalability**

   * Automatically scales with workloads.

5. **Security**

   * Built-in secrets management.

6. **Cost Efficient**

   * Free usage for public repositories.

---

## 🔁 CI to CD (Future Scope)

Currently, this project implements **Continuous Integration (CI)**.

This can be extended to **Continuous Deployment (CD)** using tools like:

* Argo CD

### How CD Works:

1. Docker image is pushed to registry.
2. Kubernetes manifests are updated with new image.
3. Argo CD syncs changes automatically.
4. Application is deployed to Kubernetes cluster.

---

## 📌 Conclusion

This project demonstrates a modern CI pipeline using GitHub Actions with:

* Automated build
* Code quality checks
* Security scanning
* Docker image creation

It follows industry best practices and can be extended to a full CI/CD pipeline using Argo CD.

---

## 🔐 Secrets & Versioning Strategy

### GitHub Secrets Used

Sensitive credentials are securely stored using **GitHub Secrets**:

* `DOCKER_USERNAME` – Docker Hub username
* `DOCKER_PASSWORD` – Docker Hub password or access token

These secrets are injected during runtime and never exposed in logs or code.

---

### 🏷️ Image Versioning using Git SHA

Instead of using static tags like `latest`, this project uses **Git commit SHA** for versioning Docker images.

Example:

```
docker build -t myapp:${{ github.sha }} .
docker push myapp:${{ github.sha }}
```

### Benefits:

* Each build is uniquely identifiable
* Easy rollback to a specific version
* Improves traceability in CI/CD pipelines

---

## 👨‍💻 About Me

I am **Nitheesh Kumar Bellamkonda**, a DevOps Engineer with around **3 years of hands-on experience** in building and managing CI/CD pipelines, automation, and cloud-based infrastructure.

I have practical experience working with tools like:

* GitHub Actions & Jenkins for CI/CD
* Docker & Kubernetes for containerization and orchestration
* AWS for cloud infrastructure
* SonarQube & Snyk for security and code quality

In this project, I designed and implemented a complete CI pipeline using a **self-hosted GitHub Actions runner**, integrating build automation, security scanning, and containerization.

I focus on writing clean, efficient pipelines and follow best practices like:

* Secure credential management using secrets
* Automated vulnerability scanning
* Version-controlled deployments using Git SHA

🎯 My goal is to build scalable, secure, and production-ready DevOps solutions and continuously improve my skills in modern tools like Kubernetes, Argo CD, and AI-integrated DevOps.

---

## 📌 Conclusion

This project demonstrates a modern CI pipeline using GitHub Actions with:

* Automated build
* Code quality checks
* Security scanning
* Docker image creation
* Secure secrets handling
* Versioned artifacts using Git SHA

It follows industry best practices and can be extended to a full CI/CD pipeline using Argo CD.

---
