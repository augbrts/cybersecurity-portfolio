# DevSecOps Project – Phase 1: Secure SDLC

This project demonstrates the integration of security practices early in the Software Development Lifecycle (SDLC) by building and analyzing a simple vulnerable application.

The goal is to apply a **shift-left security approach**, identifying and mitigating vulnerabilities before deployment.

---

## Objective

* Build a simple web application
* Introduce a controlled vulnerability
* Containerize the application using Docker
* Perform vulnerability scanning
* Document findings and mitigation

---

## Tech Stack

* Python (Flask)
* Docker
* Trivy (vulnerability scanner)
* Linux

---

## Application Overview

The application is a simple login system developed for demonstration purposes.

It intentionally includes insecure input handling to simulate a common vulnerability scenario.

---

## Project Structure

[ADD PRINT HERE – structure.png]

> Project structure showing a containerized application with defined components (app, Dockerfile, dependencies).

---

## Vulnerability Introduced

**Type:** Improper Input Validation

The application does not properly sanitize user input, which may allow malicious data to be processed.

[ADD PRINT HERE – code.png]

> The application directly reflects user input without validation, demonstrating insecure coding practices that may lead to XSS or injection attacks.

---

## Running the Application

### 1. Build Docker Image

```bash
docker build -t devsecops-app .
```

[ADD PRINT HERE – docker-build.png]

> Docker image build process, ensuring a consistent and reproducible environment.

---

### 2. Run Container

```bash
docker run -p 5000:5000 devsecops-app
```

---

### 3. Access Application

http://localhost:5000

[ADD PRINT HERE – app-running.png]

> Application running locally inside a container, exposing a login interface.

---

## Security Testing

### Input Validation Test

Example input used:

```bash
<script>alert(1)</script>
```

[ADD PRINT HERE – xss-test.png]

> The application reflects user input without sanitization, indicating a potential cross-site scripting (XSS) vulnerability.

---

## Vulnerability Scanning

### Run Trivy Scan

```bash
trivy image devsecops-app
```

[ADD PRINT HERE – trivy-scan.png]

> Scan results highlighting vulnerabilities in dependencies and the container image.

---

## Findings

* Outdated dependencies detected
* Vulnerabilities in base image
* Lack of input validation in application logic

---

## Mitigation (Next Steps)

* Implement input validation and sanitization
* Update dependencies to secure versions
* Use secure base images
* Add automated security checks in CI/CD pipeline

---

## Key Learning Outcomes

* Understanding of Secure SDLC principles
* Practical exposure to container security
* Identification of common vulnerabilities
* Importance of early security integration

---

## Next Phase

Phase 2 – CI/CD Pipeline Integration
Phase 3 – DevSecOps Pipeline

---

## Author

Augusto Bretas
https://linkedin.com/in/augusto-bretas/
https://github.com/augbrts
