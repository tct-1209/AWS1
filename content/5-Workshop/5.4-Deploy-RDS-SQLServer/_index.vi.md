---
title: "Tri?n khai database v?i Amazon RDS SQL Server"
date: 2026-07-01
weight: 4
chapter: false
pre: " <b> 5.4. </b> "
---

# Tri?n khai database v?i Amazon RDS SQL Server

Khi backend du?c tri?n khai l�n EC2, c?u h�nh database local kh�ng c�n ph� h?p v� `localhost` l�c n�y tr? t?i ch�nh m�y ch? EC2. Do d� c?n s? d?ng Amazon RDS d? cung c?p database c� th? truy c?p t? backend tr�n AWS.

<p class="workshop-img"><img src="/AWS/images/5-Workshop/5.4-Deploy-RDS-SQLServer/5-4-00-localhost-db-error.png" alt="L?i k?t n?i database local sau khi deploy EC2" style="max-width:100%;height:auto;display:block;margin:1rem auto;border:1px solid #e5e7eb;border-radius:6px;" /></p>
<p style="text-align:center;"><em>L?i k?t n?i database local sau khi deploy EC2</em></p>

#### 1. T?o Amazon RDS SQL Server

Amazon RDS SQL Server d� du?c t?o th�nh c�ng v� chuy?n sang tr?ng th�i **Available**. Database s?n s�ng d? backend Spring Boot tr�n EC2 k?t n?i.

<p class="workshop-img"><img src="/AWS/images/5-Workshop/5.4-Deploy-RDS-SQLServer/5-4-01-rds-available.png" alt="Amazon RDS SQL Server Available" style="max-width:100%;height:auto;display:block;margin:1rem auto;border:1px solid #e5e7eb;border-radius:6px;" /></p>
<p style="text-align:center;"><em>Amazon RDS SQL Server Available</em></p>

#### 2. L?y endpoint c?a RDS

L?y endpoint c?a Amazon RDS SQL Server d? c?u h�nh k?t n?i database cho backend Spring Boot tr�n EC2.

<p class="workshop-img"><img src="/AWS/images/5-Workshop/5.4-Deploy-RDS-SQLServer/5-4-02-rds-endpoint.png" alt="L?y endpoint RDS SQL Server" style="max-width:100%;height:auto;display:block;margin:1rem auto;border:1px solid #e5e7eb;border-radius:6px;" /></p>
<p style="text-align:center;"><em>L?y endpoint RDS SQL Server</em></p>

#### 3. T?o database cho d? �n

T?o database `clothing_store_backend` th�nh c�ng tr�n Amazon RDS SQL Server. Database n�y du?c backend Spring Boot s? d?ng d? luu tr? d? li?u ngu?i d�ng, s?n ph?m, gi? h�ng, don h�ng v� c�c th�ng tin nghi?p v? c?a h? th?ng.

<p class="workshop-img"><img src="/AWS/images/5-Workshop/5.4-Deploy-RDS-SQLServer/5-4-03-database-created.png" alt="T?o database clothing_store_backend" style="max-width:100%;height:auto;display:block;margin:1rem auto;border:1px solid #e5e7eb;border-radius:6px;" /></p>
<p style="text-align:center;"><em>T?o database clothing_store_backend</em></p>

V� d? l?nh k?t n?i RDS b?ng `sqlcmd`:

```bash
sqlcmd -S "<RDS_PRIVATE_IP_OR_ENDPOINT>,1433" -U <DB_USERNAME> -C -l 120
```

Sau khi v�o SQL Server prompt, t?o ho?c ki?m tra database:

```sql
SELECT name FROM sys.databases;
GO
```

#### 4. C?p nh?t file `.env` d? d�ng RDS

C?p nh?t file `.env` tr�n EC2 d? backend Spring Boot k?t n?i t?i Amazon RDS SQL Server thay v� database local.

<p class="workshop-img"><img src="/AWS/images/5-Workshop/5.4-Deploy-RDS-SQLServer/5-4-04-env-rds.png" alt="C?p nh?t .env k?t n?i RDS" style="max-width:100%;height:auto;display:block;margin:1rem auto;border:1px solid #e5e7eb;border-radius:6px;" /></p>
<p style="text-align:center;"><em>C?p nh?t .env k?t n?i RDS</em></p>

{{% notice warning %}}
Kh�ng dua m?t kh?u database th?t l�n b�o c�o ho?c source public. N�n d�ng bi?n m�i tru?ng trong `.env` ho?c secret manager n?u tri?n khai production.
{{% /notice %}}








