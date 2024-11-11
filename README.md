![Alt Text](https://github.com/lann87/cloud_infra_eng_ntu_coursework_alanp/blob/main/.misc/ntu_logo.png)  

# DevSecOps - Assignment 3.12 - Continuous Deployment Container

## Individual Assignment - Implement CD of containers with Terraform

**Date**: 4 Nov  
**Author**: Alan Peh  

## ECS deployment with Terraform and CICD pipeline  

This project demonstrate the implmentation of a CI/CD pipeline for ECS, using Terraform IaC and GitHub Actions for workflow automation.  

### 1. Structure

```sh
.
├── terraform/
│   ├── ecs.tf       # AWS ECS function configuration
│   ├── ecr.tf          # AWS ECR Repository function configuration
│   ├── vpc.tf     # Sets up AWS provider and TF dependencies
│   ├── network.tf      # S3 backend for TF state storage
│   ├── alb.tf      # S3 backend for TF state storage
│   ├── provider.tf      # S3 backend for TF state storage
│   └── backend.tf     # Lambda function invocation output
├── python/
│   ├── lambda_function.py      # Python code for Lambda function logic
│   └── lambda_function.zip     # Zipped Python code and dependencies for Lambda deployment
├── .github/
│   └── workflows/
│       ├── checkov.yaml        # Security scans with Checkov on TF code
│       ├── ci-ecs-4nov.yaml    # Continuous Integration: Terraform fmt/init/validate/lint on pull requests
│       └── cd-ecs-4nov.yaml    # Continuous Deployment: Terraform plan on PRs, apply on merge to main
├── resource/
│   └── screenshots             # Folder for screenshots, e.g., for documentation
└── README.md                   # Documentation for the project and submission
```

### 2. Github Actions Workflows  

GitHub Actions Workflows: 