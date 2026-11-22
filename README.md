# DevSecOps Jenkins Pipeline

This repository demonstrates a DevSecOps CI/CD pipeline using Jenkins, Docker, automated testing, and security scanning tools.

## Overview

The project showcases how application code can be validated, tested, scanned, and packaged through a Jenkins pipeline before deployment.

Pipeline stages include:

- Dependency Installation
- Automated Testing
- SonarQube Analysis
- Quality Gate Validation
- OWASP Dependency Check
- Trivy Security Scan
- Docker Image Build

## Architecture

GitHub
   |
   v
Jenkins Pipeline
   |
   +--> Install Dependencies
   |
   +--> Run Unit Tests
   |
   +--> SonarQube Analysis
   |
   +--> Quality Gate Validation
   |
   +--> OWASP Dependency Check
   |
   +--> Trivy Security Scan
   |
   +--> Docker Image Build
   |
   v
Docker Image

## Repository Structure

devsecops-jenkins-pipeline

app/
└── app.py

tests/
└── test_app.py

reports/

Dockerfile

Jenkinsfile

requirements.txt

README.md

## Security Controls

### SonarQube

Performs static code analysis and code quality validation.

### OWASP Dependency Check

Identifies known vulnerabilities in application dependencies.

### Trivy

Scans container images for security vulnerabilities and misconfigurations.

## Technologies Used

- Jenkins
- Docker
- Python
- Flask
- Pytest
- SonarQube
- OWASP Dependency Check
- Trivy
- Git
- GitHub

## Features

- CI/CD Automation
- Automated Unit Testing
- Code Quality Validation
- Dependency Vulnerability Scanning
- Container Security Scanning
- Docker Image Versioning
- Security-Focused Pipeline Design

## Future Enhancements

- Container Image Registry Integration
- Kubernetes Deployment
- Security Policy Enforcement
- Automated Release Management
