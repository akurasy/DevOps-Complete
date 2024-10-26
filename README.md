# Complete DevOps Project in Deploying a Full-Stack FastAPI and React Template

Welcome to the Full-Stack FastAPI and React template application deployed on Amazon Web Services (AWS) Elastic Kubernetes Service (EKS). This document provides a detailed introduction and instruction to the deployment, highlighting the key components and technologies involved. This repository serves as a demo project for a complete end-to-end DevOps processes, ranging from infrastructure provisioning using terraform, unit test code, vulnerability scanning, containerization, image scan, container orchestration, logging, monitoring and alert system, showcasing how to use various DevOps technology to set up and run a full-stack application with a Postgres Database, FastAPI backend and a ReactJS frontend using ChakraUI.

Welcome to the official README for the Three-tier Fastapi Application

Application: This application is containerized as a Docker image on Amazon ECR private repository  and deployed on AWS EKS using Kubernetes.

## Deployment Structure
The deployment consist of the following components
# Components

| Component                  |  |
|----------------------------|----------|
| 1. VPC                     |    ✅   |
| 2. Private and Public Subnets |  ✅   |
| 3. Route Tables            |    ✅   |
| 4. NAT Gateways            |    ✅   |
| 5. Load Balancers          |    ✅   |
| 6. EC2 Instance (Node)     |    ✅   |
| 7. EKS                     |    ✅   |

| Component                  | Required |
|----------------------------|----------|
| 1 Service                     |    ✅   |
| 1 Deployment |  ✅   |
| 3 Pods            |    ✅   |

## Getting Started 

### Prerequisites

Before you begin, ensure you have the following prerequisites in place:

1. **Ubuntu Linux Machine**: This Deployment is designed to run on an Ubuntu Linux machine. Ensure you have an Ubuntu-based system available.

2. **AWS CLI Installed and Access Keys Configured**: To interact with AWS services, you'll need the AWS Command Line Interface (CLI) installed on your machine. Additionally, configure your AWS access keys to authenticate with AWS. You can set up access keys using the `aws configure` command.

3. **Terraform Installed**: This project relies on Terraform for infrastructure provisioning. Make sure you have Terraform installed on your Ubuntu machine. You can find installation instructions for Terraform on the [official Terraform website](https://www.terraform.io/downloads.html).

4. **Kubectl Installed**:   This project requires kubectl to run kubernetes deployment command. It allows you to send a querry to the kubernetes api. Install Kubectl by [visiting this official kubernetes documentation](https://kubernetes.io/docs/tasks/tools/install-kubectl-linux/)

5. **Helm Installed**: Helm is required for managing multiple production environment like dev, staging, qa and prod. helm can be installed b visiting the [helm offical documentation](https://helm.sh/docs/intro/install/)



# STEP1
clone this repository into your server by running the command 

```
git clone https://github.com/akurasy/devops-complete.git
```
