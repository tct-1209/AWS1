---
title: "Test the full workflow and VNPay payment"
date: 2026-07-01
weight: 8
chapter: false
pre: " <b> 5.8. </b> "
---

# Test the full workflow and VNPay payment

After the frontend, backend, and database are deployed, test the complete workflow of the SUMMER-STORE system.

<p class="workshop-img"><img src="/AWS/images/5-Workshop/5.1-Workshop-overview/5-1-01-workflow-aws.png" alt="Overall SUMMER-STORE workflow on AWS" style="max-width:100%;height:auto;display:block;margin:1rem auto;border:1px solid #e5e7eb;border-radius:6px;" /></p>
<p style="text-align:center;"><em>Overall SUMMER-STORE workflow on AWS</em></p>

#### Main test flow

1. Access the SUMMER-STORE website through the S3 website endpoint.
2. Log in with a user or admin account.
3. The frontend calls the backend API through the Elastic IP `13.223.11.215:8080`.
4. The EC2 backend processes business logic and reads/writes data to Amazon RDS for SQL Server.
5. The user creates an order and selects VNPay Sandbox payment.
6. The backend creates the payment URL and redirects the user to VNPay.
7. After payment, VNPay redirects/calls back to the backend.
8. The backend updates the order status in the database.

#### Results achieved

- The frontend website is accessible from the Internet through Amazon S3.
- The Spring Boot backend runs on Amazon EC2.
- The backend API works through the Elastic IP and port 8080.
- Amazon RDS for SQL Server stores system data.
- Product images are stored and displayed from Amazon S3.
- Login, product management, inventory, order management, and VNPay Sandbox payment are tested at demo level.

