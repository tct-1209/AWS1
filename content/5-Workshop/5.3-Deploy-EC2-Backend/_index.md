---
title: "Deploy the Spring Boot backend on Amazon EC2"
date: 2026-07-01
weight: 3
chapter: false
pre: " <b> 5.3. </b> "
---

# Deploy the Spring Boot backend on Amazon EC2

In this step, the Spring Boot backend of the project is deployed to Amazon EC2. EC2 acts as the server that runs the backend application, receives requests from the frontend, and connects to the RDS database.

#### 1. Create an EC2 instance

Create an EC2 instance to deploy the Spring Boot backend of the project.

<p class="workshop-img"><img src="/AWS/images/5-Workshop/5.3-Deploy-EC2-Backend/5-3-01-ec2-instance.png" alt="Create an EC2 instance" style="max-width:100%;height:auto;display:block;margin:1rem auto;border:1px solid #e5e7eb;border-radius:6px;" /></p>
<p style="text-align:center;"><em>Create an EC2 instance</em></p>

#### 2. Configure the EC2 Security Group

Configure the Security Group for EC2. Port `22` is used for SSH, port `8080` is used to run the Spring Boot backend, and ports `80/443` can be used for HTTP and HTTPS if the system is extended later.

<p class="workshop-img"><img src="/AWS/images/5-Workshop/5.3-Deploy-EC2-Backend/5-3-02-security-group-ec2.png" alt="Configure the EC2 Security Group" style="max-width:100%;height:auto;display:block;margin:1rem auto;border:1px solid #e5e7eb;border-radius:6px;" /></p>
<p style="text-align:center;"><em>Configure the EC2 Security Group</em></p>

#### 3. Connect to EC2 by SSH

Connect successfully to EC2 through SSH to install the environment and deploy the backend.

<p class="workshop-img"><img src="/AWS/images/5-Workshop/5.3-Deploy-EC2-Backend/5-3-03-ssh-connection.png" alt="SSH connection to EC2" style="max-width:100%;height:auto;display:block;margin:1rem auto;border:1px solid #e5e7eb;border-radius:6px;" /></p>
<p style="text-align:center;"><em>SSH connection to EC2</em></p>

Example SSH command:

```bash
ssh -i "backend.pem" ubuntu@13.223.11.215
```

#### 4. Install Java 17

Install Java 17 on EC2 to run the Spring Boot application.

<p class="workshop-img"><img src="/AWS/images/5-Workshop/5.3-Deploy-EC2-Backend/5-3-04-java17.png" alt="Check Java 17 on EC2" style="max-width:100%;height:auto;display:block;margin:1rem auto;border:1px solid #e5e7eb;border-radius:6px;" /></p>
<p style="text-align:center;"><em>Check Java 17 on EC2</em></p>

#### 5. Build the backend with Maven

Build the Spring Boot backend successfully with Maven. The `.jar` file is created in the `target` directory and prepared for deployment to Amazon EC2.

<p class="workshop-img"><img src="/AWS/images/5-Workshop/5.3-Deploy-EC2-Backend/5-3-05-maven-build.png" alt="Build the backend with Maven" style="max-width:100%;height:auto;display:block;margin:1rem auto;border:1px solid #e5e7eb;border-radius:6px;" /></p>
<p style="text-align:center;"><em>Build the backend with Maven</em></p>

Example build command:

```bash
./mvnw clean package -DskipTests
```

#### 6. Check the `.jar` file after the build

The `.jar` file created after the build process is the artifact used to deploy the backend to EC2.

<p class="workshop-img"><img src="/AWS/images/5-Workshop/5.3-Deploy-EC2-Backend/5-3-06-target-jar.png" alt="JAR file in the target directory" style="max-width:100%;height:auto;display:block;margin:1rem auto;border:1px solid #e5e7eb;border-radius:6px;" /></p>
<p style="text-align:center;"><em>JAR file in the target directory</em></p>

#### 7. Upload the `.jar` file to EC2

Upload the Spring Boot backend `.jar` file from the local machine to EC2 using SCP. The file is renamed to `app.jar` for easier management on the server.

<p class="workshop-img"><img src="/AWS/images/5-Workshop/5.3-Deploy-EC2-Backend/5-3-07-upload-app-jar.png" alt="Upload app.jar to EC2" style="max-width:100%;height:auto;display:block;margin:1rem auto;border:1px solid #e5e7eb;border-radius:6px;" /></p>
<p style="text-align:center;"><em>Upload app.jar to EC2</em></p>

Example upload command:

```bash
scp -i "backend.pem" target/clothing-store-backend-0.0.1-SNAPSHOT.jar ubuntu@13.223.11.215:/home/ubuntu/clothing-store/app.jar
```

#### 8. Create the `.env` file on EC2

Create a `.env` file on EC2 to store environment variables required by the backend, such as RDS configuration, JWT, email, image storage, and VNPay. The `.env` file is placed in the same directory as `app.jar` so that Spring Boot can read the configuration when starting.

<p class="workshop-img"><img src="/AWS/images/5-Workshop/5.3-Deploy-EC2-Backend/5-3-08-env-file.png" alt="Create the .env file on EC2" style="max-width:100%;height:auto;display:block;margin:1rem auto;border:1px solid #e5e7eb;border-radius:6px;" /></p>
<p style="text-align:center;"><em>Create the .env file on EC2</em></p>

