---
title: "B?n d? xu?t"
date: 2026-07-01
weight: 2
chapter: false
pre: " <b> 2. </b> "
---

# B?n d? xu?t tri?n khai d? �n SUMMER-STORE tr�n AWS

## 1. T�n d? t�i

**Tri?n khai website thuong m?i di?n t? SUMMER-STORE tr�n n?n t?ng AWS**

D? �n t?p trung v�o vi?c dua h? th?ng website b�n qu?n �o **SUMMER-STORE** t? m�i tru?ng local l�n AWS. H? th?ng bao g?m frontend React/Vite, backend Spring Boot, database SQL Server v� ch?c nang thanh to�n th? nghi?m qua VNPay Sandbox.

## 2. L� do ch?n d? t�i

Trong th?c t?, m?t website thuong m?i di?n t? kh�ng ch? c?n ch?y du?c tr�n m�y local m� c�n c?n c� kh? nang truy c?p qua Internet, luu tr? d? li?u t?p trung, x? l� API ?n d?nh v� d? theo d�i chi ph� v?n h�nh. V� v?y, d? t�i n�y du?c l?a ch?n nh?m th?c h�nh quy tr�nh tri?n khai m?t h? th?ng fullstack l�n cloud th�ng qua c�c d?ch v? AWS co b?n.

Vi?c tri?n khai SUMMER-STORE tr�n AWS gi�p sinh vi�n hi?u r� hon c�ch k?t h?p **Amazon S3**, **Amazon EC2**, **Amazon RDS**, **Elastic IP**, **IAM**, **AWS CLI**, **CloudWatch** v� **AWS Budgets** trong m?t b�i to�n g?n v?i th?c t?.

## 3. M?c ti�u d? t�i

- Tri?n khai frontend React/Vite b?ng **Amazon S3 Static Website Hosting**.
- Tri?n khai backend Spring Boot tr�n **Amazon EC2**.
- S? d?ng **Amazon RDS for SQL Server** d? luu d? li?u h? th?ng.
- C?u h�nh **Elastic IP** d? c? d?nh d?a ch? truy c?p API backend.
- C?u h�nh **Security Group** cho SSH, API backend v� k?t n?i database.
- Luu tr? ?nh s?n ph?m b?ng **Amazon S3**.
- Ki?m th? c�c ch?c nang ch�nh: dang nh?p, qu?n l� s?n ph?m, t?n kho, don h�ng v� thanh to�n VNPay Sandbox.
- Theo d�i ho?t d?ng v� chi ph� b?ng **CloudWatch**, **AWS Budgets** v� **Billing**.

## 4. Ph?m vi th?c hi?n

Ph?m vi d? t�i t?p trung v�o tri?n khai h? th?ng ? m?c demo/th?c t?p. C�c ch?c nang ch�nh g?m dang k�, dang nh?p, hi?n th? s?n ph?m, qu?n l� s?n ph?m, qu?n l� bi?n th?, qu?n l� t?n kho, qu?n l� don h�ng v� thanh to�n th? nghi?m b?ng VNPay Sandbox.

�? t�i chua tri?n khai c�c th�nh ph?n n�ng cao nhu Load Balancer, Auto Scaling, Route 53, CloudFront CDN ho?c CI/CD t? d?ng ho�n ch?nh. Nh?ng th�nh ph?n n�y c� th? du?c b? sung trong giai do?n m? r?ng sau.

## 5. Ki?n tr�c d? xu?t

Ngu?i d�ng ho?c admin truy c?p website th�ng qua tr�nh duy?t. Frontend du?c host tr�n **Amazon S3 Static Website Hosting**. Sau khi t?i giao di?n v? tr�nh duy?t, ?ng d?ng React/Vite g?i API t?i backend th�ng qua **Elastic IP** c?a EC2. Backend Spring Boot ch?y tr�n **Amazon EC2**, x? l� nghi?p v? v� k?t n?i t?i **Amazon RDS SQL Server** d? d?c/ghi d? li?u. V?i ch?c nang thanh to�n, backend t?o URL thanh to�n VNPay Sandbox v� nh?n redirect/callback d? c?p nh?t tr?ng th�i don h�ng.

<p class="workshop-img"><img src="/AWS/images/2-Proposal/summer-store-workflow.png" alt="Workflow tri?n khai SUMMER-STORE tr�n AWS" style="max-width:100%;height:auto;display:block;margin:1rem auto;border:1px solid #e5e7eb;border-radius:6px;" /></p>
<p style="text-align:center;"><em>Workflow tri?n khai SUMMER-STORE tr�n AWS</em></p>

## 6. C�c d?ch v? AWS s? d?ng

| D?ch v? | Vai tr� trong d? �n |
|---|---|
| **Amazon S3 Static Website Hosting** | Host frontend React/Vite g?m `index.html`, JavaScript, CSS v� t�i nguy�n tinh. |
| **Amazon S3 Product Images Bucket** | Luu tr? ?nh s?n ph?m v� media c?a h? th?ng. |
| **Amazon EC2** | Ch?y backend Spring Boot b?ng file `app.jar`. |
| **Elastic IP** | C? d?nh d?a ch? backend API, v� d? `13.223.11.215:8080`. |
| **Amazon RDS for SQL Server** | Luu tr? d? li?u ngu?i d�ng, s?n ph?m, gi? h�ng, don h�ng v� bi?n th? s?n ph?m. |
| **Security Group** | Ki?m so�t truy c?p port `22`, `8080`, `80/443` v� `1433`. |
| **AWS IAM** | Qu?n l� user, quy?n truy c?p v� access key cho AWS CLI. |
| **AWS CLI** | H? tr? start/stop EC2, ki?m tra tr?ng th�i t�i nguy�n v� thao t�c v?i AWS t? m�y local. |
| **Amazon CloudWatch** | Theo d�i log v� tr?ng th�i v?n h�nh co b?n. |
| **AWS Budgets / Billing** | Theo d�i credit v� chi ph� s? d?ng AWS. |

## 7. Thi?t k? th�nh ph?n

### 7.1 Frontend

Frontend du?c ph�t tri?n b?ng React/Vite. Sau khi build, c�c file static trong thu m?c `dist` du?c upload l�n S3 bucket frontend d? ngu?i d�ng c� th? truy c?p website qua S3 website endpoint.

<p class="workshop-img"><img src="/AWS/images/2-Proposal/s3-frontend-success.png" alt="Frontend tri?n khai tr�n Amazon S3" style="max-width:100%;height:auto;display:block;margin:1rem auto;border:1px solid #e5e7eb;border-radius:6px;" /></p>
<p style="text-align:center;"><em>Frontend SUMMER-STORE sau khi tri?n khai l�n Amazon S3</em></p>

### 7.2 Backend

Backend du?c ph�t tri?n b?ng Spring Boot. ?ng d?ng du?c build th�nh file `.jar`, upload l�n EC2 v� ch?y b?ng Java 17. Backend ti?p nh?n request t? frontend, x? l� nghi?p v? v� tr? d? li?u API cho website.

<p class="workshop-img"><img src="/AWS/images/2-Proposal/ec2-backend-instance.png" alt="Amazon EC2 ch?y backend Spring Boot" style="max-width:100%;height:auto;display:block;margin:1rem auto;border:1px solid #e5e7eb;border-radius:6px;" /></p>
<p style="text-align:center;"><em>Amazon EC2 du?c s? d?ng d? tri?n khai backend Spring Boot</em></p>

### 7.3 Database

Database s? d?ng Amazon RDS for SQL Server. Backend k?t n?i d?n RDS th�ng qua JDBC d? luu tr? v� truy v?n d? li?u nhu t�i kho?n ngu?i d�ng, s?n ph?m, bi?n th? s?n ph?m, gi? h�ng v� don h�ng.

<p class="workshop-img"><img src="/AWS/images/2-Proposal/rds-sqlserver-available.png" alt="Amazon RDS SQL Server" style="max-width:100%;height:auto;display:block;margin:1rem auto;border:1px solid #e5e7eb;border-radius:6px;" /></p>
<p style="text-align:center;"><em>Amazon RDS SQL Server ? tr?ng th�i Available</em></p>

### 7.4 Thanh to�n

VNPay Sandbox l� d?ch v? thanh to�n b�n ngo�i AWS. Backend t?o payment URL, chuy?n ngu?i d�ng sang trang thanh to�n VNPay v� nh?n k?t qu? redirect/callback d? c?p nh?t tr?ng th�i don h�ng trong database.

## 8. K? ho?ch tri?n khai

| Giai do?n | N?i dung th?c hi?n |
|---|---|
| Giai do?n 1 | Chu?n b? m� ngu?n frontend, backend, t�i kho?n AWS, IAM user v� AWS CLI. |
| Giai do?n 2 | T?o EC2, c?u h�nh Security Group, c�i Java 17 v� deploy backend Spring Boot. |
| Giai do?n 3 | T?o Amazon RDS SQL Server, t?o database `clothing_store_backend` v� c?p nh?t file `.env`. |
| Giai do?n 4 | T?o S3 bucket luu ?nh s?n ph?m v� c?u h�nh bucket policy ph� h?p. |
| Giai do?n 5 | Build frontend React/Vite, upload file static l�n S3 v� b?t Static Website Hosting. |
| Giai do?n 6 | G?n Elastic IP, ki?m th? API, dang nh?p, qu?n l� s?n ph?m, don h�ng v� VNPay Sandbox. |
| Giai do?n 7 | Theo d�i v?n h�nh, ki?m tra chi ph� v� d?n d?p t�i nguy�n kh�ng c?n thi?t. |

## 9. K?t qu? mong d?i

Sau khi ho�n th�nh, h? th?ng SUMMER-STORE c� th? ho?t d?ng tr�n m�i tru?ng AWS v?i c�c k?t qu? sau:

- Ngu?i d�ng truy c?p du?c frontend th�ng qua S3 website endpoint.
- Frontend g?i du?c API backend th�ng qua Elastic IP.
- Backend Spring Boot ch?y ?n d?nh tr�n EC2 b?ng `systemd service`.
- D? li?u du?c luu tr? v� truy v?n t? Amazon RDS SQL Server.
- Admin c� th? qu?n l� s?n ph?m, t?n kho v� don h�ng.
- Ngu?i d�ng c� th? d?t h�ng v� thanh to�n th? nghi?m qua VNPay Sandbox.
- Ngu?i th?c hi?n n?m du?c quy tr�nh tri?n khai website fullstack l�n AWS v� c�ch theo d�i chi ph� cloud.

## 10. R?i ro v� hu?ng x? l�

| R?i ro | Hu?ng x? l� |
|---|---|
| Backend kh�ng truy c?p du?c t? frontend | Ki?m tra Security Group, port `8080`, Elastic IP v� CORS. |
| EC2 kh�ng k?t n?i du?c RDS | Ki?m tra endpoint RDS, port `1433`, Security Group v� th�ng tin `.env`. |
| ?nh s?n ph?m kh�ng hi?n th? | Ki?m tra S3 bucket policy, object URL v� quy?n public read n?u c?n. |
| VNPay Sandbox l?i callback | Ki?m tra `returnUrl`, m� c?u h�nh VNPay v� ch? k� b?o m?t. |
| Chi ph� AWS vu?t d? ki?n | Theo d�i Billing/Budgets, stop EC2/RDS khi kh�ng s? d?ng. |

## 11. Hu?ng m? r?ng

Trong tuong lai, h? th?ng c� th? du?c m? r?ng b?ng c�ch s? d?ng **CloudFront** d? tang t?c frontend, **Route 53** d? g?n t�n mi?n ri�ng, **Application Load Balancer** v� **Auto Scaling** d? tang d? s?n s�ng cho backend, cung nhu tri?n khai CI/CD d? t? d?ng build v� deploy m� ngu?n.







