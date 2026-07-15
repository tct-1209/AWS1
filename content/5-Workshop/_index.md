---
title: "SUMMER-STORE Deployment Workshop on AWS"
date: 2026-07-01
weight: 5
chapter: false
pre: " <b> 5. </b> "
---

# Deploying the SUMMER-STORE E-commerce Website on AWS

#### Overview

This workshop presents the process of deploying the **SUMMER-STORE** project from a local environment to AWS. The system includes a React/Vite frontend, a Spring Boot backend, and a SQL Server database. The AWS services used in the project include **Amazon S3**, **Amazon EC2**, **Amazon RDS for SQL Server**, **Elastic IP**, **IAM**, **AWS CLI**, **Amazon CloudWatch**, and **AWS Budgets**.

#### Deployment architecture

Users access the website through the frontend hosted with **Amazon S3 Static Website Hosting**. After the frontend is loaded in the browser, the React/Vite application calls the backend API through the **Elastic IP** attached to **Amazon EC2**. The Spring Boot backend processes business logic and connects to **Amazon RDS for SQL Server** to read and write data. For payment, the backend creates a **VNPay Sandbox** payment URL and receives the redirect/callback to update the order status.

<p class="workshop-img"><img src="/AWS/images/5-Workshop/5.1-Workshop-overview/5-1-01-workflow-aws.png" alt="SUMMER-STORE deployment workflow on AWS" style="max-width:100%;height:auto;display:block;margin:1rem auto;border:1px solid #e5e7eb;border-radius:6px;" /></p>
<p style="text-align:center;"><em>SUMMER-STORE deployment workflow on AWS</em></p>

#### Contents

1. [Workshop overview](5.1-Workshop-overview/)
2. [Deployment prerequisites](5.2-Prerequiste/)
3. [Deploy the Spring Boot backend on Amazon EC2](5.3-Deploy-EC2-Backend/)
4. [Deploy the database with Amazon RDS for SQL Server](5.4-Deploy-RDS-SQLServer/)
5. [Store product images with Amazon S3](5.5-S3-Product-Images/)
6. [Deploy the React frontend with Amazon S3 Static Website Hosting](5.6-Deploy-S3-Frontend/)
7. [Test the backend, Elastic IP, and API](5.7-ElasticIP-Systemd-Test/)
8. [Test the full workflow and VNPay payment](5.8-Workflow-Final-Test/)
9. [Clean up resources](5.9-Cleanup/)

