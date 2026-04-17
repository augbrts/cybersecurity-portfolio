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

## Vulnerability Introduced

**Type:** Improper Input Validation

The application does not properly sanitize user input, which may allow malicious data to be processed.

This simulates real-world insecure coding practices found in early-stage applications.

---

## Project Structure

```
devsecops-project/
│
├── app/
│   └── app.py
│
├── Dockerfile
├── requirements.txt
└── README.md
```

---

## Running the Application

### 1. Build Docker Image

```
docker build -t devsecops-app .
```

---

### 2. Run Container

```
docker run -p 5000:5000 devsecops-app
```

---

### 3. Access Application

Open in browser:

```
http://localhost:5000
```

---

## Vulnerability Scanning

### Run Trivy Scan

```
trivy image devsecops-app
```

---

## Findings

* Outdated dependencies detected
* Potential vulnerabilities in base image
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

This project will evolve into:

**Phase 2 – CI/CD Pipeline Integration**

* Automating build and test processes

**Phase 3 – DevSecOps Pipeline**

* Integrating security checks into CI/CD

---

## Author

Augusto Bretas
https://linkedin.com/in/augusto-bretas/
https://github.com/augbrts
