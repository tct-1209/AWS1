---
title: "Test the backend, Elastic IP, and API"
date: 2026-07-01
weight: 7
chapter: false
pre: " <b> 5.7. </b> "
---

# Test the backend, Elastic IP, and API

After deploying the backend to EC2 and configuring the frontend to call the API through the Elastic IP, test port 8080, the API endpoint, and the backend application status.

#### 1. Test port 8080 from the local machine

Test the connection from the local machine to the EC2 backend through port `8080`. The result `TcpTestSucceeded: True` confirms that the Security Group and network allow external access to the API.

<p class="workshop-img"><img src="/aws/images/5-Workshop/5.7-ElasticIP-Systemd-Test/5-7-01-test-port-8080.png" alt="Test port 8080 from the local machine" style="max-width:100%;height:auto;display:block;margin:1rem auto;border:1px solid #e5e7eb;border-radius:6px;" /></p>
<p style="text-align:center;"><em>Test port 8080 from the local machine</em></p>

Example PowerShell command:

```powershell
Test-NetConnection 13.223.11.215 -Port 8080
```

#### 2. Test the `/v3/api-docs` endpoint

The `/v3/api-docs` endpoint returns OpenAPI JSON, confirming that the Spring Boot backend is publicly available on EC2 through port 8080.

<p class="workshop-img"><img src="/aws/images/5-Workshop/5.7-ElasticIP-Systemd-Test/5-7-02-api-docs-browser.png" alt="Test api-docs in the browser" style="max-width:100%;height:auto;display:block;margin:1rem auto;border:1px solid #e5e7eb;border-radius:6px;" /></p>
<p style="text-align:center;"><em>Test api-docs in the browser</em></p>

#### 3. Test directly on EC2

Testing directly on EC2 shows that the backend is running on port `8080` and the `/v3/api-docs` endpoint returns HTTP 200.

<p class="workshop-img"><img src="/aws/images/5-Workshop/5.7-ElasticIP-Systemd-Test/5-7-03-curl-api-docs.png" alt="curl localhost api-docs on EC2" style="max-width:100%;height:auto;display:block;margin:1rem auto;border:1px solid #e5e7eb;border-radius:6px;" /></p>
<p style="text-align:center;"><em>curl localhost api-docs on EC2</em></p>

Example command:

```bash
curl -I http://localhost:8080/v3/api-docs
```

#### 4. Check deployment files on EC2

The `app.jar` file is the Spring Boot backend artifact that has been built and uploaded to EC2. The `.env` file stores environment variables such as RDS configuration, JWT, email, image storage, and VNPay.

<p class="workshop-img"><img src="/aws/images/5-Workshop/5.7-ElasticIP-Systemd-Test/5-7-04-app-env-final.png" alt="Check app.jar and .env on EC2" style="max-width:100%;height:auto;display:block;margin:1rem auto;border:1px solid #e5e7eb;border-radius:6px;" /></p>
<p style="text-align:center;"><em>Check app.jar and .env on EC2</em></p>

#### 5. Run the backend with systemd service

To keep the backend running after closing SSH/PowerShell, create the `clothing-store-backend` service with systemd.

Useful service commands:

```bash
sudo systemctl restart clothing-store-backend
sudo systemctl status clothing-store-backend --no-pager
```

When the service shows `active (running)`, the backend continues to run even after the SSH terminal is closed.
