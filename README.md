# AWS Lambda Deployment using Jenkins and AWS SAM

This project demonstrates how to deploy a **Hello World AWS Lambda function** using **AWS SAM (Serverless Application Model)** and automate the deployment process using **Jenkins CI/CD pipeline**.

The goal of this project is to understand how **CI/CD works with serverless applications** by integrating Jenkins with AWS services in a secure and automated way.

---

##  Project Overview

- Created a **Hello World AWS Lambda function** using AWS SAM
- Wrote a **Jenkinsfile** to automate:
  - Code checkout from GitHub
  - Build and package the SAM application
  - Deploy the Lambda function to AWS
- Used **IAM roles and Jenkins credentials** instead of hardcoding AWS keys
- Implemented a simple but realistic **CI/CD pipeline for serverless deployment**

---

##  Tech Stack

- **AWS Lambda**
- **AWS SAM CLI**
- **Jenkins**
- **GitHub**
- **Python** (Lambda runtime)
- **Linux (Ubuntu)**
- **AWS CLI**


---

##  Prerequisites

Before running this project, make sure you have:

- AWS account
- IAM user/role with permissions for:
  - Lambda
  - CloudFormation
  - S3
  - IAM
- Jenkins installed and running
- AWS CLI configured on Jenkins server
- AWS SAM CLI installed
- Git installed

---

##  CI/CD Workflow

1. Developer pushes code to GitHub
2. Jenkins pulls the latest code
3. Jenkins runs the pipeline defined in `Jenkinsfile`
4. AWS SAM:
   - Builds the Lambda function
   - Packages the application
   - Deploys it using CloudFormation
5. Lambda function is deployed successfully on AWS

---

##  Security Best Practices Followed

- **No AWS access keys hardcoded**
- Jenkins uses **stored credentials**
- AWS CLI is configured securely
- `.aws/credentials` is not pushed to GitHub

---

##  How to Run Manually (Optional)

```bash
sam build
sam deploy --guided
