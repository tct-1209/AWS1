---
title: "Workshop overview"
date: 2026-07-01
weight: 1
chapter: false
pre: " <b> 5.1. </b> "
---

# Workshop overview

This workshop focuses on deploying the **SUMMER-STORE** e-commerce website to AWS. The project originally runs locally and is then moved to the cloud so that users can access the frontend over the Internet, the backend can run on EC2, and the data can be stored in Amazon RDS for SQL Server.

#### Objectives

- Deploy the Spring Boot backend on **Amazon EC2**.
- Use **Amazon RDS for SQL Server** as the main database.
- Host the React/Vite frontend with **Amazon S3 Static Website Hosting**.
- Attach an **Elastic IP** to keep the backend address stable.
- Configure Security Groups for SSH, backend API access, and database access.
- Test login, product management, inventory, orders, and VNPay Sandbox payment.
- Monitor operations and cost with CloudWatch, Budgets, and Billing.

#### Overall workflow

<p class="workshop-img"><img src="/AWS/images/5-Workshop/5.1-Workshop-overview/5-1-01-workflow-aws.png" alt="SUMMER-STORE deployment workflow on AWS" style="max-width:100%;height:auto;display:block;margin:1rem auto;border:1px solid #e5e7eb;border-radius:6px;" /></p>
<p style="text-align:center;"><em>SUMMER-STORE deployment workflow on AWS</em></p>

#### Main application flow

1. **User/Admin accesses the website** through a browser.
2. **Amazon S3 serves the frontend**, including `index.html`, JavaScript, CSS, and images.
3. **The frontend calls the backend API** through the Elastic IP `13.223.11.215:8080`.
4. **Amazon EC2 processes business logic** and connects to Amazon RDS for SQL Server to read/write data.
5. **VNPay Sandbox handles payment**, then redirects/calls back to the backend to update the order status.

