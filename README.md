# Sample Spring Boot CI/CD Project

Hello World Spring Boot application with full CI/CD using **Jenkins + AWS ECR + Kubernetes**.

## Project Structure
- `app/sample-spring-boot-app/` → Spring Boot application
- `docker/Dockerfile` → Multistage Dockerfile
- `k8s/dev/` & `k8s/qa/` → Kubernetes manifests
- `ci/Jenkinsfile` → Complete CI/CD pipeline

## GitHub Flow
- `main` → Production-ready branch (protected)
- `feature/*` → All new work

**Branch Protection Rules (recommended)**:
- Require Pull Request before merging to main
- Require status checks to pass
- Require code review

## How to Run Locally
```bash
cd app/sample-spring-boot-app
mvn spring-boot:run
