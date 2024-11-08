# 4nov-ecs-cicd

```sh
.
├── terraform/
│   ├── ecs.tf       # Defines AWS Lambda function configuration
│   ├── ecr.tf          # IAM roles and policies required for Lambda
│   ├── vpc.tf     # Sets up AWS provider and TF dependencies
│   ├── backend.tf      # S3 backend for TF state storage
│   └── alb.tf     # Lambda function invocation output
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