# 🚀 Enterprise DevSecOps CI/CD Pipeline

An end-to-end automated **DevSecOps CI/CD Pipeline** designed for cloud-native web applications. This project demonstrates continuous integration, static code analysis, vulnerability scanning, containerization, and orchestration using **Jenkins, SonarQube, OWASP Dependency-Check, Trivy, Docker, and Kubernetes**.

---

## 📌 Features & Architecture

- **Automated Workflows:** End-to-end automation from code checkout to Kubernetes deployment using Jenkins Declarative Pipelines.
- **Code Quality & Static Analysis:** Integrated **SonarQube** with automated Quality Gates to enforce coding standards.
- **Multi-Layer Security Scanning:**
  - **OWASP Dependency-Check:** Identifies vulnerabilities in third-party libraries.
  - **Trivy (FS & Image):** Scans file systems and Docker images for OS/application package vulnerabilities.
- **Containerization:** Dockerized application build using dynamic arguments and pushed to Docker Hub.
- **Orchestration:** Automated deployment to **Kubernetes** using declarative deployment and service manifests.
- **Notifications:** Automated post-build email alerts with attached Trivy security reports.

---

## 🛠️ Tech Stack & Tools

- **CI/CD Orchestration:** Jenkins
- **Version Control:** Git, GitHub
- **Code Quality & Security:** SonarQube, OWASP Dependency-Check, Trivy
- **Containerization & Registry:** Docker, Docker Hub
- **Orchestration:** Kubernetes (kubectl)
- **Languages & Frameworks:** Groovy (Jenkinsfile), Node.js / Java

---

## ⚙️ Pipeline Stages

1. **Clean Workspace & Checkout:** Cleans the working directory and pulls the latest source code.
2. **SonarQube Analysis & Quality Gate:** Scans code quality and waits for Quality Gate approval.
3. **Dependency Installation & OWASP Scan:** Installs packages and audits third-party dependencies.
4. **Trivy File System Scan:** Scans source code files for vulnerabilities.
5. **Docker Build & Push:** Securely builds the container image and pushes it to Docker Hub.
6. **Trivy Image Scan:** Audits the generated container image.
7. **Container Deployment:** Runs local container testing.
8. **Kubernetes Deployment:** Applies Kubernetes `deployment.yml` and `service.yml` to the cluster.
9. **Post-Build Actions:** Sends email notifications along with scan logs (`trivyfs.txt`, `trivyimage.txt`).

---

## 🚀 Getting Started

1. **Prerequisites:**
   - Jenkins server with required plugins installed (SonarQube Scanner, Docker, Kubernetes CLI, OWASP Dependency-Check, Email Extension).
   - Docker & Kubernetes cluster access.
   - SonarQube server setup.

2. **Pipeline Parameters:**
   - `GIT_REPO_URL`: Source repository link.
   - `GIT_BRANCH`: Target branch (default: `main`).
   - `DOCKER_USER`: Docker Hub username.
   - `IMAGE_NAME`: Docker image name.
   - `IMAGE_TAG`: Docker image tag.
   - `APP_PORT`: Exposed host port.
   - `NOTIFICATION_EMAIL`: Alert recipient email.

---

## 📄 License

This project is open-source and available under the [MIT License](LICENSE).