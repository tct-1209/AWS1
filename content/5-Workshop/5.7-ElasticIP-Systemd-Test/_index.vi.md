---
title: "Ki?m th? backend, Elastic IP v� API"
date: 2026-07-01
weight: 7
chapter: false
pre: " <b> 5.7. </b> "
---

# Ki?m th? backend, Elastic IP v� API

Sau khi tri?n khai backend l�n EC2 v� c?u h�nh frontend g?i API qua Elastic IP, c?n ki?m tra port 8080, endpoint API v� tr?ng th�i ch?y c?a ?ng d?ng backend.

#### 1. Ki?m tra port 8080 t? m�y local

Ki?m tra k?t n?i t? m�y local t?i backend EC2 qua port `8080`. K?t qu? `TcpTestSucceeded: True` x�c nh?n Security Group v� network d� cho ph�p truy c?p API t? b�n ngo�i.

<p class="workshop-img"><img src="/AWS/images/5-Workshop/5.7-ElasticIP-Systemd-Test/5-7-01-test-port-8080.png" alt="Test port 8080 t? m�y local" style="max-width:100%;height:auto;display:block;margin:1rem auto;border:1px solid #e5e7eb;border-radius:6px;" /></p>
<p style="text-align:center;"><em>Test port 8080 t? m�y local</em></p>

V� d? l?nh PowerShell:

```powershell
Test-NetConnection 13.223.11.215 -Port 8080
```

#### 2. Ki?m tra endpoint `/v3/api-docs`

Endpoint `/v3/api-docs` tr? v? t�i li?u OpenAPI JSON, x�c nh?n backend Spring Boot d� public API th�nh c�ng tr�n EC2 th�ng qua port 8080.

<p class="workshop-img"><img src="/AWS/images/5-Workshop/5.7-ElasticIP-Systemd-Test/5-7-02-api-docs-browser.png" alt="Ki?m tra api-docs tr�n tr�nh duy?t" style="max-width:100%;height:auto;display:block;margin:1rem auto;border:1px solid #e5e7eb;border-radius:6px;" /></p>
<p style="text-align:center;"><em>Ki?m tra api-docs tr�n tr�nh duy?t</em></p>

#### 3. Ki?m tra tr?c ti?p tr�n EC2

Ki?m tra tr?c ti?p tr�n EC2 cho th?y backend dang ch?y ?n d?nh ? port `8080` v� endpoint `/v3/api-docs` tr? v? HTTP 200.

<p class="workshop-img"><img src="/AWS/images/5-Workshop/5.7-ElasticIP-Systemd-Test/5-7-03-curl-api-docs.png" alt="curl localhost api-docs tr�n EC2" style="max-width:100%;height:auto;display:block;margin:1rem auto;border:1px solid #e5e7eb;border-radius:6px;" /></p>
<p style="text-align:center;"><em>curl localhost api-docs tr�n EC2</em></p>

V� d? l?nh ki?m tra:

```bash
curl -I http://localhost:8080/v3/api-docs
```

#### 4. Ki?m tra file tri?n khai tr�n EC2

File `app.jar` l� backend Spring Boot d� du?c build v� upload l�n EC2. File `.env` luu c�c bi?n m�i tru?ng nhu c?u h�nh RDS, JWT, email, luu tr? ?nh v� VNPay.

<p class="workshop-img"><img src="/AWS/images/5-Workshop/5.7-ElasticIP-Systemd-Test/5-7-04-app-env-final.png" alt="Ki?m tra app.jar v� .env tr�n EC2" style="max-width:100%;height:auto;display:block;margin:1rem auto;border:1px solid #e5e7eb;border-radius:6px;" /></p>
<p style="text-align:center;"><em>Ki?m tra app.jar v� .env tr�n EC2</em></p>

#### 5. Ch?y backend b?ng systemd service

�? backend lu�n ch?y sau khi d�ng SSH/PowerShell, t?o service `clothing-store-backend` b?ng systemd.

M?t s? l?nh ki?m tra service:

```bash
sudo systemctl restart clothing-store-backend
sudo systemctl status clothing-store-backend --no-pager
```

Khi service hi?n th? `active (running)`, backend c� th? ti?p t?c ho?t d?ng k? c? khi d�ng terminal SSH.





