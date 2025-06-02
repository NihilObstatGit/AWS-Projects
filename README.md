# ☁️ AWS Cloud + Security Portfolio Projects (Q1-Q4 2025)

Welcome to my curated set of foundational AWS projects designed to showcase cloud, security, and automation skills aligned with real-world use cases. These projects are beginner-to-intermediate in scope and demonstrate my readiness for cloud engineering, DevSecOps, and security analyst roles.

---

## 🧩 Project Index

| Project | Focus Area | Key AWS Services |
|--------|-------------|------------------|
| [1. Static Website Hosting](#1-static-website-hosting) | Web + DNS + CDN | S3, Route 53, CloudFront, IAM |
| [2. Serverless Contact App](#2-serverless-contact-app) | API + Email | Lambda, API Gateway, SES |
| [3. IAM Policy Generator](#3-iam-policy-generator) | Security Automation | Python (Boto3), IAM, GitHub Actions |
| [4. Vulnerability Logging Pipeline](#4-vulnerability-logging-pipeline) | Compliance + Alerting | AWS Config, CloudTrail, Lambda, Athena |
| [5. 3-Tier Web Architecture](#5-three-tier-web-app-architecture) | Architecture + Networking | EC2, RDS, VPC, Auto Scaling, ELB |
| [6. Cloud Resume Challenge](#6-cloud-resume-challenge) | Full-stack Infra-as-Code | S3, DynamoDB, Lambda, Route 53, GitHub Actions |

---

## 🔧 1. Static Website Hosting
**Description**: Host a static portfolio site with global delivery and HTTPS.
- **S3**: Stores and serves HTML/CSS
- **Route 53**: DNS routing for custom domain
- **CloudFront**: Distributes content via CDN
- **ACM**: Provides free SSL certificates
- **IAM**: Secures access via bucket policies

📁 `/static-website-hosting`

---

## ✉️ 2. Serverless Contact App
**Description**: A secure, scalable API that allows users to submit messages via a frontend form.
- **API Gateway**: Handles HTTP requests
- **Lambda**: Executes form-processing logic
- **SES**: Sends emails securely from backend
- **IAM**: Restricts service permissions

📁 `/serverless-contact-app`

---

## 🔐 3. IAM Policy Generator
**Description**: A Python CLI to generate and validate least-privilege IAM policies.
- **Boto3**: Python SDK for AWS
- **IAM**: Policy management and testing
- **GitHub Actions**: Automates tests and linting

📁 `/iam-policy-generator`

---

## 🕵️‍♂️ 4. Vulnerability Logging Pipeline
**Description**: Detect and log public S3 buckets or security violations using AWS native services.
- **AWS Config**: Monitors misconfigurations
- **CloudTrail**: Logs API activity
- **Lambda**: Processes findings to S3
- **Athena**: Queries logs in S3 with SQL
- **SNS** (optional): Alerts via email or Slack

📁 `/vuln-logging-pipeline`

---

## 🏗️ 5. Three-Tier Web App Architecture
**Description**: A modular infrastructure for web applications following AWS best practices.
- **EC2**: Frontend app servers
- **RDS**: Relational backend (MySQL/PostgreSQL)
- **VPC**: Network segmentation with subnets, NAT
- **ELB**: Load balances traffic to EC2
- **Auto Scaling**: Handles demand spikes

📁 `/three-tier-web-architecture`

---

## 📈 6. Cloud Resume Challenge
**Description**: A resume site powered by AWS, CI/CD, and cloud-native tech.
- **S3**: Hosts static frontend
- **Route 53**: Custom domain setup
- **DynamoDB**: Stores visitor counter
- **Lambda**: Updates DB on page load
- **GitHub Actions**: Automates build & deployment
- **CloudWatch**: Logs and metrics for uptime/debugging

📁 `/cloud-resume-challenge`

---

## 🗺️ Architecture Overview

```mermaid
graph TD
    A[User] -->|DNS| B[Route 53]
    B --> C[S3 Bucket]
    B --> D[CloudFront CDN]
    D --> C
    A -->|Submit Form| E[API Gateway]
    E --> F[Lambda Function]
    F --> G[SES / Email Notification]
    F --> H[DynamoDB Visitor Counter]

    subgraph Logging and Security
        I[AWS Config] --> J[S3 Logs]
        K[CloudTrail] --> J
        L[Lambda for Alerts] --> J
        M[Athena] --> J
    end

    subgraph 3-Tier App
        N[ELB] --> O[EC2 Frontend]
        O --> P[RDS Database]
        O --> Q[VPC with Subnets]
    end
