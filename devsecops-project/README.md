# DevSecOps Project – Phase 1: Secure SDLC

This project demonstrates the integration of security practices early in the Software Development Lifecycle (SDLC) by building and analyzing a simple vulnerable application.

The goal is to apply a **shift-left security approach**, identifying and understanding vulnerabilities before deployment.

---

## Objective

* Build a simple web application
* Introduce a controlled vulnerability
* Containerize the application using Docker
* Perform vulnerability scanning

---

## Tech Stack

* Python (Flask)
* Docker
* Trivy
* Linux

---

## Application Overview

A simple login application was developed for demonstration purposes.
The application intentionally lacks proper input validation to simulate insecure coding practices.

---

## Vulnerability

**Type:** Improper Input Validation

The application reflects user input directly without sanitization, which may allow malicious input such as scripts or injection payloads.

### Evidence

[ADD PRINT 1 – code.png]

> Vulnerable code where user input is returned without validation.

---

## Running the Application

### Build Image

```bash
docker build -t devsecops-app .
```

### Run Container

```bash
docker run -p 5000:5000 devsecops-app
```

[ADD PRINT 2 – docker-run.png]

> Container running locally, exposing the application.

---

## Application Execution

Access the application at:

http://localhost:5000

[ADD PRINT 3 – app-running.png]

> Web application interface running in the browser.

---

## Security Testing

A test input was used to evaluate how the application handles user input:

```html
<script>alert(1)</script>
```

[ADD PRINT 4 – xss-test.png]

> The application reflects the input directly, indicating lack of sanitization and potential XSS vulnerability.

---

## Vulnerability Scanning

The container image was scanned using Trivy:

```bash
trivy image devsecops-app
```

[ADD PRINT 5 – trivy-scan.png]

> Scan results identifying vulnerabilities in the container image and dependencies.

---

## Key Learnings

* Importance of Secure SDLC practices
* Risks of improper input validation
* Basics of container security
* Introduction to vulnerability scanning

---

## Next Steps

* Implement input validation and sanitization
* Update dependencies
* Integrate CI/CD pipeline
* Add automated security checks

---

## Author

Augusto Bretas
https://linkedin.com/in/augusto-bretas/
https://github.com/augbrts
