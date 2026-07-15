---
title: "Triá»ƒn khai database vá»›i Amazon RDS SQL Server"
date: 2026-07-01
weight: 4
chapter: false
pre: " <b> 5.4. </b> "
---

# Triá»ƒn khai database vá»›i Amazon RDS SQL Server

Khi backend Ä‘Æ°á»£c triá»ƒn khai lÃªn EC2, cáº¥u hÃ¬nh database local khÃ´ng cÃ²n phÃ¹ há»£p vÃ¬ `localhost` lÃºc nÃ y trá» tá»›i chÃ­nh mÃ¡y chá»§ EC2. Do Ä‘Ã³ cáº§n sá»­ dá»¥ng Amazon RDS Ä‘á»ƒ cung cáº¥p database cÃ³ thá»ƒ truy cáº­p tá»« backend trÃªn AWS.

<p class="workshop-img"><img src="/AWS/images/5-Workshop/5.4-Deploy-RDS-SQLServer/5-4-00-localhost-db-error.png" alt="Lá»—i káº¿t ná»‘i database local sau khi deploy EC2" style="max-width:100%;height:auto;display:block;margin:1rem auto;border:1px solid #e5e7eb;border-radius:6px;" /></p>
<p style="text-align:center;"><em>Lá»—i káº¿t ná»‘i database local sau khi deploy EC2</em></p>

#### 1. Táº¡o Amazon RDS SQL Server

Amazon RDS SQL Server Ä‘Ã£ Ä‘Æ°á»£c táº¡o thÃ nh cÃ´ng vÃ  chuyá»ƒn sang tráº¡ng thÃ¡i **Available**. Database sáºµn sÃ ng Ä‘á»ƒ backend Spring Boot trÃªn EC2 káº¿t ná»‘i.

<p class="workshop-img"><img src="/AWS/images/5-Workshop/5.4-Deploy-RDS-SQLServer/5-4-01-rds-available.png" alt="Amazon RDS SQL Server Available" style="max-width:100%;height:auto;display:block;margin:1rem auto;border:1px solid #e5e7eb;border-radius:6px;" /></p>
<p style="text-align:center;"><em>Amazon RDS SQL Server Available</em></p>

#### 2. Láº¥y endpoint cá»§a RDS

Láº¥y endpoint cá»§a Amazon RDS SQL Server Ä‘á»ƒ cáº¥u hÃ¬nh káº¿t ná»‘i database cho backend Spring Boot trÃªn EC2.

<p class="workshop-img"><img src="/AWS/images/5-Workshop/5.4-Deploy-RDS-SQLServer/5-4-02-rds-endpoint.png" alt="Láº¥y endpoint RDS SQL Server" style="max-width:100%;height:auto;display:block;margin:1rem auto;border:1px solid #e5e7eb;border-radius:6px;" /></p>
<p style="text-align:center;"><em>Láº¥y endpoint RDS SQL Server</em></p>

#### 3. Táº¡o database cho dá»± Ã¡n

Táº¡o database `clothing_store_backend` thÃ nh cÃ´ng trÃªn Amazon RDS SQL Server. Database nÃ y Ä‘Æ°á»£c backend Spring Boot sá»­ dá»¥ng Ä‘á»ƒ lÆ°u trá»¯ dá»¯ liá»‡u ngÆ°á»i dÃ¹ng, sáº£n pháº©m, giá» hÃ ng, Ä‘Æ¡n hÃ ng vÃ  cÃ¡c thÃ´ng tin nghiá»‡p vá»¥ cá»§a há»‡ thá»‘ng.

<p class="workshop-img"><img src="/AWS/images/5-Workshop/5.4-Deploy-RDS-SQLServer/5-4-03-database-created.png" alt="Táº¡o database clothing_store_backend" style="max-width:100%;height:auto;display:block;margin:1rem auto;border:1px solid #e5e7eb;border-radius:6px;" /></p>
<p style="text-align:center;"><em>Táº¡o database clothing_store_backend</em></p>

VÃ­ dá»¥ lá»‡nh káº¿t ná»‘i RDS báº±ng `sqlcmd`:

```bash
sqlcmd -S "<RDS_PRIVATE_IP_OR_ENDPOINT>,1433" -U <DB_USERNAME> -C -l 120
```

Sau khi vÃ o SQL Server prompt, táº¡o hoáº·c kiá»ƒm tra database:

```sql
SELECT name FROM sys.databases;
GO
```

#### 4. Cáº­p nháº­t file `.env` Ä‘á»ƒ dÃ¹ng RDS

Cáº­p nháº­t file `.env` trÃªn EC2 Ä‘á»ƒ backend Spring Boot káº¿t ná»‘i tá»›i Amazon RDS SQL Server thay vÃ¬ database local.

<p class="workshop-img"><img src="/AWS/images/5-Workshop/5.4-Deploy-RDS-SQLServer/5-4-04-env-rds.png" alt="Cáº­p nháº­t .env káº¿t ná»‘i RDS" style="max-width:100%;height:auto;display:block;margin:1rem auto;border:1px solid #e5e7eb;border-radius:6px;" /></p>
<p style="text-align:center;"><em>Cáº­p nháº­t .env káº¿t ná»‘i RDS</em></p>

{{% notice warning %}}
KhÃ´ng Ä‘Æ°a máº­t kháº©u database tháº­t lÃªn bÃ¡o cÃ¡o hoáº·c source public. NÃªn dÃ¹ng biáº¿n mÃ´i trÆ°á»ng trong `.env` hoáº·c secret manager náº¿u triá»ƒn khai production.
{{% /notice %}}

