# AWS Demo App 1

This repository contains the code and configurations for `aws-demo-app-2`, a demo application designed to be deployed on AWS using various AWS services such as EKS, RDS, and ECR.

## Table of Contents

- [Prerequisites](#prerequisites)
- [Environment Setup](#environment-setup)
- [Build and Deployment](#build-and-deployment)
- [Project Structure](#project-structure)
- [Contributing](#contributing)
- [License](#license)

## Prerequisites

- [Node.js](https://nodejs.org/) installed.
- [Docker](https://www.docker.com/) installed.
- AWS CLI configured with appropriate permissions.
- Kubernetes cluster set up and configured (EKS in this case).
- Amazon ECR repository created for storing Docker images.

## Environment Setup

1. **Clone the repository**:
    ```sh
    git clone https://github.com/benbenbuhben/aws-demo-app-2.git
    cd aws-demo-app-2
    ```

2. **Create a `.env` file**:
    Create a `.env` file in the root directory and add the following environment variables:
    ```env
    DB_HOST=your_database_host
    DB_USER=your_database_user
    DB_PASSWORD=your_database_password
    DB_NAME=your_database_name
    ```

## Build and Deployment

The application uses AWS CodeBuild and CodePipeline for CI/CD, and Kubernetes for deployment. Below are the high-level steps to build and deploy the application.

1. **Configure AWS CodeBuild**:
    The `buildspec.yml` file contains the build instructions for CodeBuild. It includes steps for installing dependencies, logging into Amazon ECR, building the Docker image, pushing the image to ECR, and deploying the application to EKS.

2. **Deploy to Kubernetes**:
    Use the provided Kubernetes configuration files (`deployment.yml`, `service.yml`, `ingress.yml`) to deploy the application.

## Project Structure

```plaintext
.
├── .env
├── buildspec.yml
├── deployment.yml
├── Dockerfile
├── index.js
├── package.json
├── service.yml
├── ingress.yml
└── README.md
