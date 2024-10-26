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



# STEP1 (Infrastructure Provisioning)
Before you begin this, a basic understanding of terraform is required. Look into the terraform script and change the variables to suite your deployment
clone this repository into your server by running the command 

```
git clone https://github.com/akurasy/devops-complete.git
```

change directory to the terraform directory where all infrastructure code is kept.

```
cd Terraform
```

run the following commands to provision your infrastructure 

```
terraform init
terraform plan
terraform apply --auto-approve
```

# STEP2 (Connect to the cluster and run your Continous Integration with Github Actions)

connect the cluster with the command 

```
aws eks update-kubeconfig --name zik-cluster --region us-east-1

#the name of my cluster is zik-cluster and the cluster is deployed in us-east-1 region
```

After connecting to the cluster, we need to set up our CI using Github Actions to run the unit test code, scan the application for vulnerability using sonarqube, build the application with docker, scan our docker image with trivy and push the image to ECR repository. before deploying this CI, we need to set up a sonarqube server using docker. install docker and deploy sonarqube using the commands below

```
sudo apt install docker.io -y  #docker installation
```

```
sudo docker run -d --name sonar -p 9000:9000 sonarqube #this will deploy sonarqube with latest tag
```

browse sonarqube with the public IP address of your server on port 9000

http://Public-IP-Address:9000

login username = admin

login password = admin123


goto this repository, click on actions and open a workflow tab to write your pipeline. You can give the flow anyname you want, but the workflow directory has ther naming convention ".github/workflows/name-of-workflow.yaml" .
