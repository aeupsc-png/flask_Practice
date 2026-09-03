# Flask Student Registration System – CI/CD Deployment

## Project Overview

This project is a Flask-based Student Registration System that uses MongoDB as the backend database.

The project demonstrates a complete DevOps CI/CD workflow using GitHub Actions, Docker, Amazon ECR, Amazon EC2, AWS IAM, GitHub OIDC authentication, and AWS Systems Manager (SSM).

Whenever changes are pushed to the `main` branch, the GitHub Actions pipeline automatically:

1. Runs automated tests.
2. Builds the Docker image.
3. Authenticates with AWS using GitHub OIDC.
4. Pushes the Docker image to Amazon ECR.
5. Deploys the application to the EC2 instance using AWS Systems Manager.
6. Runs the Flask application inside a Docker container.

---

## Features

- Add student records
- View student records
- Update student records
- Delete student records
- MongoDB database integration
- Bootstrap-based user interface
- Docker containerization
- Automated CI/CD pipeline
- Automated Docker image build
- Amazon ECR image storage
- Automated EC2 deployment using AWS Systems Manager
- Docker container restart policy

---

## Technology Stack

### Application

- Python 3.12
- Flask
- Flask-PyMongo
- MongoDB
- Jinja2
- Bootstrap 5

### DevOps

- Git
- GitHub
- GitHub Actions
- Docker
- Amazon ECR
- Amazon EC2
- AWS Systems Manager
- AWS IAM
- GitHub OIDC

---

# Architecture

The CI/CD workflow follows this architecture:

```text
Developer
    |
    | git push
    v
GitHub Repository
    |
    v
GitHub Actions
    |
    +----------------------+
    |                      |
    v                      v
Run Tests              Build Docker Image
    |                      |
    |                      v
    |                 Amazon ECR
    |                      |
    |                      v
    +--------------> AWS Systems Manager
                           |
                           v
                       EC2 Instance
                           |
                           v
                    Docker Container
                           |
                           v
                  Flask Application
                           |
                           v
                        MongoDB
