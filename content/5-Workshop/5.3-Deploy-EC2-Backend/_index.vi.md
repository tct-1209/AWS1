---
title: "Tri?n khai Backend Spring Boot tr�n Amazon EC2"
date: 2026-07-01
weight: 3
chapter: false
pre: " <b> 5.3. </b> "
---

# Tri?n khai Backend Spring Boot tr�n Amazon EC2

? bu?c n�y, backend Spring Boot c?a d? �n du?c tri?n khai l�n Amazon EC2. EC2 d�ng vai tr� l� server ch?y ?ng d?ng backend, ti?p nh?n request t? frontend v� k?t n?i t?i database RDS.

#### 1. Kh?i t?o EC2 Instance

Kh?i t?o EC2 Instance d? tri?n khai backend Spring Boot c?a d? �n.

<p class="workshop-img"><img src="/AWS/images/5-Workshop/5.3-Deploy-EC2-Backend/5-3-01-ec2-instance.png" alt="Kh?i t?o EC2 Instance" style="max-width:100%;height:auto;display:block;margin:1rem auto;border:1px solid #e5e7eb;border-radius:6px;" /></p>
<p style="text-align:center;"><em>Kh?i t?o EC2 Instance</em></p>

#### 2. C?u h�nh Security Group cho EC2

C?u h�nh Security Group cho EC2. Port `22` d�ng d? SSH, port `8080` d�ng d? ch?y backend Spring Boot, port `80/443` d�ng cho HTTP v� HTTPS n?u c?n m? r?ng.

<p class="workshop-img"><img src="/AWS/images/5-Workshop/5.3-Deploy-EC2-Backend/5-3-02-security-group-ec2.png" alt="C?u h�nh Security Group cho EC2" style="max-width:100%;height:auto;display:block;margin:1rem auto;border:1px solid #e5e7eb;border-radius:6px;" /></p>
<p style="text-align:center;"><em>C?u h�nh Security Group cho EC2</em></p>

#### 3. K?t n?i EC2 b?ng SSH

K?t n?i th�nh c�ng v�o EC2 th�ng qua SSH d? c�i d?t m�i tru?ng v� tri?n khai backend.

<p class="workshop-img"><img src="/AWS/images/5-Workshop/5.3-Deploy-EC2-Backend/5-3-03-ssh-connection.png" alt="K?t n?i SSH v�o EC2" style="max-width:100%;height:auto;display:block;margin:1rem auto;border:1px solid #e5e7eb;border-radius:6px;" /></p>
<p style="text-align:center;"><em>K?t n?i SSH v�o EC2</em></p>

V� d? l?nh SSH:

```bash
ssh -i "backend.pem" ubuntu@13.223.11.215
```

#### 4. C�i d?t Java 17

C�i d?t Java 17 tr�n EC2 d? ch?y ?ng d?ng Spring Boot.

<p class="workshop-img"><img src="/AWS/images/5-Workshop/5.3-Deploy-EC2-Backend/5-3-04-java17.png" alt="Ki?m tra Java 17 tr�n EC2" style="max-width:100%;height:auto;display:block;margin:1rem auto;border:1px solid #e5e7eb;border-radius:6px;" /></p>
<p style="text-align:center;"><em>Ki?m tra Java 17 tr�n EC2</em></p>

#### 5. Build backend b?ng Maven

Build backend Spring Boot th�nh c�ng b?ng Maven. File `.jar` du?c t?o trong thu m?c `target` d? chu?n b? tri?n khai l�n Amazon EC2.

<p class="workshop-img"><img src="/AWS/images/5-Workshop/5.3-Deploy-EC2-Backend/5-3-05-maven-build.png" alt="Build backend b?ng Maven" style="max-width:100%;height:auto;display:block;margin:1rem auto;border:1px solid #e5e7eb;border-radius:6px;" /></p>
<p style="text-align:center;"><em>Build backend b?ng Maven</em></p>

V� d? l?nh build:

```bash
./mvnw clean package -DskipTests
```

#### 6. Ki?m tra file `.jar` sau khi build

File `.jar` du?c t?o sau qu� tr�nh build, d�y l� artifact d�ng d? deploy backend l�n EC2.

<p class="workshop-img"><img src="/AWS/images/5-Workshop/5.3-Deploy-EC2-Backend/5-3-06-target-jar.png" alt="File JAR trong thu m?c target" style="max-width:100%;height:auto;display:block;margin:1rem auto;border:1px solid #e5e7eb;border-radius:6px;" /></p>
<p style="text-align:center;"><em>File JAR trong thu m?c target</em></p>

#### 7. Upload file `.jar` l�n EC2

Upload file backend Spring Boot `.jar` t? m�y local l�n EC2 th�nh c�ng b?ng SCP. File du?c d?i t�n th�nh `app.jar` d? d? qu?n l� khi ch?y ?ng d?ng tr�n server.

<p class="workshop-img"><img src="/AWS/images/5-Workshop/5.3-Deploy-EC2-Backend/5-3-07-upload-app-jar.png" alt="Upload app.jar l�n EC2" style="max-width:100%;height:auto;display:block;margin:1rem auto;border:1px solid #e5e7eb;border-radius:6px;" /></p>
<p style="text-align:center;"><em>Upload app.jar l�n EC2</em></p>

V� d? l?nh upload:

```bash
scp -i "backend.pem" target/clothing-store-backend-0.0.1-SNAPSHOT.jar ubuntu@13.223.11.215:/home/ubuntu/clothing-store/app.jar
```

#### 8. T?o file `.env` tr�n EC2

T?o file `.env` tr�n EC2 d? luu c�c bi?n m�i tru?ng c?n thi?t cho backend nhu c?u h�nh RDS, JWT, email, luu tr? ?nh v� VNPay. File `.env` du?c d?t c�ng thu m?c v?i `app.jar` d? Spring Boot c� th? d?c c?u h�nh khi kh?i d?ng.

<p class="workshop-img"><img src="/AWS/images/5-Workshop/5.3-Deploy-EC2-Backend/5-3-08-env-file.png" alt="T?o file .env tr�n EC2" style="max-width:100%;height:auto;display:block;margin:1rem auto;border:1px solid #e5e7eb;border-radius:6px;" /></p>
<p style="text-align:center;"><em>T?o file .env tr�n EC2</em></p>





