---
title: "Chuáº©n bá»‹ triá»ƒn khai"
date: 2026-07-01
weight: 2
chapter: false
pre: " <b> 5.2. </b> "
---

# Chuáº©n bá»‹ triá»ƒn khai

TrÆ°á»›c khi triá»ƒn khai dá»± Ã¡n SUMMER-STORE lÃªn AWS, cáº§n chuáº©n bá»‹ tÃ i khoáº£n AWS, mÃ£ nguá»“n frontend/backend, key pair Ä‘á»ƒ SSH vÃ o EC2 vÃ  cÃ¡c thÃ´ng tin cáº¥u hÃ¬nh cho database, JWT, email, lÆ°u trá»¯ áº£nh vÃ  VNPay.

#### ThÃ nh pháº§n cáº§n chuáº©n bá»‹

| ThÃ nh pháº§n | Má»¥c Ä‘Ã­ch |
|---|---|
| AWS Account | Táº¡o vÃ  quáº£n lÃ½ tÃ i nguyÃªn AWS |
| IAM User / Access Key | Sá»­ dá»¥ng AWS CLI Ä‘á»ƒ start/stop EC2, kiá»ƒm tra tÃ i nguyÃªn |
| EC2 Key Pair `.pem` | SSH vÃ o EC2 Ä‘á»ƒ deploy backend |
| Backend Spring Boot | Build thÃ nh file `.jar` Ä‘á»ƒ cháº¡y trÃªn EC2 |
| Frontend React/Vite | Build thÃ nh static files Ä‘á»ƒ upload lÃªn S3 |
| RDS SQL Server | Database lÆ°u user, sáº£n pháº©m, giá» hÃ ng, Ä‘Æ¡n hÃ ng |
| VNPay Sandbox | Kiá»ƒm thá»­ luá»“ng thanh toÃ¡n |

#### CÃ¡c port cáº§n dÃ¹ng

| Port | Má»¥c Ä‘Ã­ch |
|---|---|
| 22 | SSH vÃ o EC2 |
| 8080 | Backend Spring Boot public API |
| 1433 | EC2 káº¿t ná»‘i Amazon RDS SQL Server |
| 80/443 | HTTP/HTTPS náº¿u má»Ÿ rá»™ng thÃªm domain hoáº·c reverse proxy |

{{% notice note %}}
Trong cÃ¡c file cáº¥u hÃ¬nh vÃ  cÃ¢u lá»‡nh demo, khÃ´ng nÃªn ghi trá»±c tiáº¿p máº­t kháº©u tháº­t. NÃªn dÃ¹ng placeholder nhÆ° `<DB_PASSWORD>`, `<JWT_SECRET>` hoáº·c lÆ°u trong file `.env` trÃªn EC2.
{{% /notice %}}

