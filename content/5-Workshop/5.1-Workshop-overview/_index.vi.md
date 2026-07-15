---
title: "Tá»•ng quan workshop"
date: 2026-07-01
weight: 1
chapter: false
pre: " <b> 5.1. </b> "
---

# Tá»•ng quan workshop

Pháº§n workshop táº­p trung vÃ o viá»‡c triá»ƒn khai website thÆ°Æ¡ng máº¡i Ä‘iá»‡n tá»­ **SUMMER-STORE** lÃªn AWS. Dá»± Ã¡n ban Ä‘áº§u cháº¡y local, sau Ä‘Ã³ Ä‘Æ°á»£c Ä‘Æ°a lÃªn cloud Ä‘á»ƒ ngÆ°á»i dÃ¹ng cÃ³ thá»ƒ truy cáº­p frontend qua Internet, backend hoáº¡t Ä‘á»™ng á»•n Ä‘á»‹nh trÃªn EC2 vÃ  dá»¯ liá»‡u Ä‘Æ°á»£c lÆ°u trÃªn Amazon RDS SQL Server.

#### Má»¥c tiÃªu

- Triá»ƒn khai backend Spring Boot lÃªn **Amazon EC2**.
- Sá»­ dá»¥ng **Amazon RDS SQL Server** lÃ m database chÃ­nh cho há»‡ thá»‘ng.
- Host frontend React/Vite báº±ng **Amazon S3 Static Website Hosting**.
- Cá»‘ Ä‘á»‹nh Ä‘á»‹a chá»‰ backend báº±ng **Elastic IP**.
- Cáº¥u hÃ¬nh Security Group cho SSH, API backend vÃ  database.
- Kiá»ƒm thá»­ Ä‘Äƒng nháº­p, quáº£n lÃ½ sáº£n pháº©m, tá»“n kho, Ä‘Æ¡n hÃ ng vÃ  thanh toÃ¡n VNPay Sandbox.
- Theo dÃµi váº­n hÃ nh vÃ  chi phÃ­ báº±ng CloudWatch, Budgets vÃ  Billing.

#### Workflow tá»•ng thá»ƒ

<p class="workshop-img"><img src="/AWS/images/5-Workshop/5.1-Workshop-overview/5-1-01-workflow-aws.png" alt="Workflow triá»ƒn khai SUMMER-STORE trÃªn AWS" style="max-width:100%;height:auto;display:block;margin:1rem auto;border:1px solid #e5e7eb;border-radius:6px;" /></p>
<p style="text-align:center;"><em>Workflow triá»ƒn khai SUMMER-STORE trÃªn AWS</em></p>

#### Luá»“ng hoáº¡t Ä‘á»™ng chÃ­nh

1. **User/Admin truy cáº­p website** thÃ´ng qua trÃ¬nh duyá»‡t.
2. **Amazon S3 tráº£ frontend** gá»“m `index.html`, JavaScript, CSS vÃ  hÃ¬nh áº£nh.
3. **Frontend gá»i API backend** thÃ´ng qua Elastic IP `13.223.11.215:8080`.
4. **Amazon EC2 xá»­ lÃ½ nghiá»‡p vá»¥** vÃ  káº¿t ná»‘i Amazon RDS SQL Server Ä‘á»ƒ Ä‘á»c/ghi dá»¯ liá»‡u.
5. **VNPay Sandbox xá»­ lÃ½ thanh toÃ¡n**, sau Ä‘Ã³ redirect/callback vá» backend Ä‘á»ƒ cáº­p nháº­t tráº¡ng thÃ¡i Ä‘Æ¡n hÃ ng.

