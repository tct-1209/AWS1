---
title: "Proposal"
date: 2026-07-01
weight: 2
chapter: false
pre: " <b> 2. </b> "
---

# Proposal for Deploying the SUMMER-STORE Project on AWS

## 1. Project Title

**Deploying the SUMMER-STORE E-commerce Website on AWS**

This project focuses on moving the **SUMMER-STORE** clothing e-commerce website from a local environment to AWS. The system includes a React/Vite frontend, a Spring Boot backend, a SQL Server database, product image storage, and a VNPay Sandbox payment flow.

## 2. Background and Motivation

In a real-world e-commerce system, the application should not only run locally but also be accessible over the Internet, store data centrally, expose stable APIs, and allow basic cost monitoring. This proposal was selected to practice deploying a fullstack application to the cloud using core AWS services.

Deploying SUMMER-STORE on AWS helps demonstrate how **Amazon S3**, **Amazon EC2**, **Amazon RDS**, **Elastic IP**, **IAM**, **AWS CLI**, **CloudWatch**, and **AWS Budgets** can work together in a practical web application deployment.

## 3. Objectives

- Deploy the React/Vite frontend with **Amazon S3 Static Website Hosting**.
- Deploy the Spring Boot backend on **Amazon EC2**.
- Use **Amazon RDS for SQL Server** as the main database.
- Attach an **Elastic IP** to keep the backend API address stable.
- Configure **Security Groups** for SSH, backend API access, and database access.
- Store product images using **Amazon S3**.
- Test the main features: login, product management, inventory, orders, and VNPay Sandbox payment.
- Monitor operation and cost using **CloudWatch**, **AWS Budgets**, and **Billing**.

## 4. Scope

The project scope focuses on a demo/internship-level deployment. The main features include registration, login, product display, product management, product variant management, inventory management, order management, and test payment with VNPay Sandbox.

Advanced components such as Load Balancer, Auto Scaling, Route 53, CloudFront CDN, and a complete CI/CD pipeline are not included in the current scope. These services can be added in future improvements.

## 5. Proposed Architecture

Users and admins access the website through a browser. The frontend is hosted on **Amazon S3 Static Website Hosting**. After the frontend files are loaded in the browser, the React/Vite application calls backend APIs through the **Elastic IP** attached to the EC2 instance. The Spring Boot backend runs on **Amazon EC2**, processes business logic, and connects to **Amazon RDS for SQL Server** to read and write data. For payment, the backend creates a VNPay Sandbox payment URL and receives the redirect/callback result to update the order status.

<p class="workshop-img"><img src="/AWS/images/2-Proposal/summer-store-workflow.png" alt="SUMMER-STORE deployment workflow on AWS" style="max-width:100%;height:auto;display:block;margin:1rem auto;border:1px solid #e5e7eb;border-radius:6px;" /></p>
<p style="text-align:center;"><em>SUMMER-STORE deployment workflow on AWS</em></p>

## 6. AWS Services Used

| Service | Role in the project |
|---|---|
| **Amazon S3 Static Website Hosting** | Hosts the React/Vite frontend, including `index.html`, JavaScript, CSS, and static assets. |
| **Amazon S3 Product Images Bucket** | Stores product images and media files. |
| **Amazon EC2** | Runs the Spring Boot backend using the `app.jar` file. |
| **Elastic IP** | Keeps the backend API address stable, for example `13.223.11.215:8080`. |
| **Amazon RDS for SQL Server** | Stores users, products, carts, orders, and product variants. |
| **Security Group** | Controls access to ports `22`, `8080`, `80/443`, and `1433`. |
| **AWS IAM** | Manages users, permissions, and access keys for AWS CLI. |
| **AWS CLI** | Supports starting/stopping EC2, checking resource status, and interacting with AWS from the local machine. |
| **Amazon CloudWatch** | Provides basic monitoring and logs. |
| **AWS Budgets / Billing** | Tracks AWS credits and estimated usage cost. |

## 7. Component Design

### 7.1 Frontend

The frontend is built with React/Vite. After the build process, the static files in the `dist` folder are uploaded to an S3 frontend bucket so users can access the website through the S3 website endpoint.

<p class="workshop-img"><img src="/AWS/images/2-Proposal/s3-frontend-success.png" alt="Frontend deployed on Amazon S3" style="max-width:100%;height:auto;display:block;margin:1rem auto;border:1px solid #e5e7eb;border-radius:6px;" /></p>
<p style="text-align:center;"><em>SUMMER-STORE frontend deployed on Amazon S3</em></p>

### 7.2 Backend

The backend is developed with Spring Boot. It is built into a `.jar` file, uploaded to EC2, and executed with Java 17. The backend receives requests from the frontend, processes business logic, and returns API responses to the website.

<p class="workshop-img"><img src="/AWS/images/2-Proposal/ec2-backend-instance.png" alt="Amazon EC2 running Spring Boot backend" style="max-width:100%;height:auto;display:block;margin:1rem auto;border:1px solid #e5e7eb;border-radius:6px;" /></p>
<p style="text-align:center;"><em>Amazon EC2 is used to deploy the Spring Boot backend</em></p>

### 7.3 Database

The database uses Amazon RDS for SQL Server. The backend connects to RDS through JDBC to store and query data such as user accounts, products, product variants, carts, and orders.

<p class="workshop-img"><img src="/AWS/images/2-Proposal/rds-sqlserver-available.png" alt="Amazon RDS for SQL Server" style="max-width:100%;height:auto;display:block;margin:1rem auto;border:1px solid #e5e7eb;border-radius:6px;" /></p>
<p style="text-align:center;"><em>Amazon RDS for SQL Server in Available state</em></p>

### 7.4 Payment

VNPay Sandbox is an external payment service outside AWS. The backend generates the payment URL, redirects the user to VNPay, and receives the redirect/callback result to update the order status in the database.

## 8. Implementation Plan

| Phase | Main tasks |
|---|---|
| Phase 1 | Prepare frontend source code, backend source code, AWS account, IAM user, and AWS CLI. |
| Phase 2 | Create EC2, configure Security Group, install Java 17, and deploy the Spring Boot backend. |
| Phase 3 | Create Amazon RDS for SQL Server, create the `clothing_store_backend` database, and update the `.env` file. |
| Phase 4 | Create the S3 product image bucket and configure the required bucket policy. |
| Phase 5 | Build the React/Vite frontend, upload static files to S3, and enable Static Website Hosting. |
| Phase 6 | Attach Elastic IP, test APIs, login, product management, orders, and VNPay Sandbox. |
| Phase 7 | Monitor operation, review cost, and clean up unused resources. |

## 9. Expected Results

After completion, the SUMMER-STORE system is expected to run on AWS with the following outcomes:

- Users can access the frontend through the S3 website endpoint.
- The frontend can call backend APIs through the Elastic IP.
- The Spring Boot backend runs on EC2 using a `systemd service`.
- Data is stored and retrieved from Amazon RDS for SQL Server.
- Admin users can manage products, inventory, and orders.
- Customers can place orders and perform test payments through VNPay Sandbox.
- The project owner understands the fullstack deployment process on AWS and how to monitor basic cloud cost.

## 10. Risks and Mitigation

| Risk | Mitigation |
|---|---|
| Frontend cannot call backend API | Check Security Group, port `8080`, Elastic IP, and CORS configuration. |
| EC2 cannot connect to RDS | Check RDS endpoint, port `1433`, Security Group, and `.env` database settings. |
| Product images cannot be displayed | Check S3 bucket policy, object URL, and public read configuration when required. |
| VNPay Sandbox callback fails | Check `returnUrl`, VNPay configuration values, and secure hash signature. |
| AWS cost exceeds expectation | Monitor Billing/Budgets and stop EC2/RDS when the project is not in use. |

## 11. Future Improvements

In the future, the system can be improved by adding **CloudFront** for faster frontend delivery, **Route 53** for a custom domain, **Application Load Balancer** and **Auto Scaling** for backend availability, and CI/CD for automatic build and deployment.

