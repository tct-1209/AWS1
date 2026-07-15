---
title: "Deploy the database with Amazon RDS for SQL Server"
date: 2026-07-01
weight: 4
chapter: false
pre: " <b> 5.4. </b> "
---

# Deploy the database with Amazon RDS for SQL Server

After the backend is deployed to EC2, the local database configuration is no longer suitable because `localhost` now points to the EC2 server itself. Therefore, Amazon RDS is used to provide a database that can be accessed by the backend running on AWS.

<p class="workshop-img"><img src="/aws/images/5-Workshop/5.4-Deploy-RDS-SQLServer/5-4-00-localhost-db-error.png" alt="Local database connection error after deploying to EC2" style="max-width:100%;height:auto;display:block;margin:1rem auto;border:1px solid #e5e7eb;border-radius:6px;" /></p>
<p style="text-align:center;"><em>Local database connection error after deploying to EC2</em></p>

#### 1. Create Amazon RDS for SQL Server

Amazon RDS for SQL Server is created successfully and changes to the **Available** state. The database is ready for the Spring Boot backend on EC2 to connect.

<p class="workshop-img"><img src="/aws/images/5-Workshop/5.4-Deploy-RDS-SQLServer/5-4-01-rds-available.png" alt="Amazon RDS for SQL Server Available" style="max-width:100%;height:auto;display:block;margin:1rem auto;border:1px solid #e5e7eb;border-radius:6px;" /></p>
<p style="text-align:center;"><em>Amazon RDS for SQL Server Available</em></p>

#### 2. Get the RDS endpoint

Get the Amazon RDS for SQL Server endpoint to configure the database connection for the Spring Boot backend on EC2.

<p class="workshop-img"><img src="/aws/images/5-Workshop/5.4-Deploy-RDS-SQLServer/5-4-02-rds-endpoint.png" alt="Get the RDS SQL Server endpoint" style="max-width:100%;height:auto;display:block;margin:1rem auto;border:1px solid #e5e7eb;border-radius:6px;" /></p>
<p style="text-align:center;"><em>Get the RDS SQL Server endpoint</em></p>

#### 3. Create the project database

Create the `clothing_store_backend` database successfully on Amazon RDS for SQL Server. This database is used by the Spring Boot backend to store users, products, carts, orders, and other business data.

<p class="workshop-img"><img src="/aws/images/5-Workshop/5.4-Deploy-RDS-SQLServer/5-4-03-database-created.png" alt="Create the clothing_store_backend database" style="max-width:100%;height:auto;display:block;margin:1rem auto;border:1px solid #e5e7eb;border-radius:6px;" /></p>
<p style="text-align:center;"><em>Create the clothing_store_backend database</em></p>

Example command to connect to RDS using `sqlcmd`:

```bash
sqlcmd -S "<RDS_PRIVATE_IP_OR_ENDPOINT>,1433" -U <DB_USERNAME> -C -l 120
```

After entering the SQL Server prompt, create or verify the database:

```sql
SELECT name FROM sys.databases;
GO
```

#### 4. Update the `.env` file to use RDS

Update the `.env` file on EC2 so that the Spring Boot backend connects to Amazon RDS for SQL Server instead of the local database.

<p class="workshop-img"><img src="/aws/images/5-Workshop/5.4-Deploy-RDS-SQLServer/5-4-04-env-rds.png" alt="Update .env for RDS connection" style="max-width:100%;height:auto;display:block;margin:1rem auto;border:1px solid #e5e7eb;border-radius:6px;" /></p>
<p style="text-align:center;"><em>Update .env for RDS connection</em></p>

{{% notice warning %}}
Do not publish the real database password in the report or public source code. Use environment variables in `.env` or a secret manager for production deployment.
{{% /notice %}}
