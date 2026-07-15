---
title: "Deployment prerequisites"
date: 2026-07-01
weight: 2
chapter: false
pre: " <b> 5.2. </b> "
---

# Deployment prerequisites

Before deploying SUMMER-STORE to AWS, prepare the AWS account, frontend and backend source code, EC2 key pair for SSH, and configuration values for the database, JWT, email, image storage, and VNPay.

#### Required components

| Component | Purpose |
|---|---|
| AWS Account | Create and manage AWS resources |
| IAM User / Access Key | Use AWS CLI to start/stop EC2 and check resources |
| EC2 Key Pair `.pem` | SSH into EC2 to deploy the backend |
| Spring Boot backend | Build into a `.jar` file to run on EC2 |
| React/Vite frontend | Build into static files and upload to S3 |
| RDS SQL Server | Store users, products, carts, and orders |
| VNPay Sandbox | Test the payment workflow |

#### Required ports

| Port | Purpose |
|---|---|
| 22 | SSH into EC2 |
| 8080 | Public API for the Spring Boot backend |
| 1433 | EC2 connection to Amazon RDS for SQL Server |
| 80/443 | HTTP/HTTPS if a domain or reverse proxy is added later |

{{% notice note %}}
Do not put real passwords directly in report files or demo commands. Use placeholders such as `<DB_PASSWORD>`, `<JWT_SECRET>`, or store secrets in the `.env` file on EC2.
{{% /notice %}}
