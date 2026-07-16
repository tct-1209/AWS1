---
title: "Chu?n b? tri?n khai"
date: 2026-07-01
weight: 2
chapter: false
pre: " <b> 5.2. </b> "
---

# Chu?n b? tri?n khai

Tru?c khi tri?n khai d? �n SUMMER-STORE l�n AWS, c?n chu?n b? t�i kho?n AWS, m� ngu?n frontend/backend, key pair d? SSH v�o EC2 v� c�c th�ng tin c?u h�nh cho database, JWT, email, luu tr? ?nh v� VNPay.

#### Th�nh ph?n c?n chu?n b?

| Th�nh ph?n | M?c d�ch |
|---|---|
| AWS Account | T?o v� qu?n l� t�i nguy�n AWS |
| IAM User / Access Key | S? d?ng AWS CLI d? start/stop EC2, ki?m tra t�i nguy�n |
| EC2 Key Pair `.pem` | SSH v�o EC2 d? deploy backend |
| Backend Spring Boot | Build th�nh file `.jar` d? ch?y tr�n EC2 |
| Frontend React/Vite | Build th�nh static files d? upload l�n S3 |
| RDS SQL Server | Database luu user, s?n ph?m, gi? h�ng, don h�ng |
| VNPay Sandbox | Ki?m th? lu?ng thanh to�n |

#### C�c port c?n d�ng

| Port | M?c d�ch |
|---|---|
| 22 | SSH v�o EC2 |
| 8080 | Backend Spring Boot public API |
| 1433 | EC2 k?t n?i Amazon RDS SQL Server |
| 80/443 | HTTP/HTTPS n?u m? r?ng th�m domain ho?c reverse proxy |

{{% notice note %}}
Trong c�c file c?u h�nh v� c�u l?nh demo, kh�ng n�n ghi tr?c ti?p m?t kh?u th?t. N�n d�ng placeholder nhu `<DB_PASSWORD>`, `<JWT_SECRET>` ho?c luu trong file `.env` tr�n EC2.
{{% /notice %}}





