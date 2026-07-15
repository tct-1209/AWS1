---
title: "Kiá»ƒm thá»­ workflow tá»•ng thá»ƒ vÃ  thanh toÃ¡n VNPay"
date: 2026-07-01
weight: 8
chapter: false
pre: " <b> 5.8. </b> "
---

# Kiá»ƒm thá»­ workflow tá»•ng thá»ƒ vÃ  thanh toÃ¡n VNPay

Sau khi hoÃ n táº¥t triá»ƒn khai frontend, backend vÃ  database, tiáº¿n hÃ nh kiá»ƒm thá»­ workflow tá»•ng thá»ƒ cá»§a há»‡ thá»‘ng SUMMER-STORE.

<p class="workshop-img"><img src="/AWS/images/5-Workshop/5.1-Workshop-overview/5-1-01-workflow-aws.png" alt="Workflow tá»•ng thá»ƒ SUMMER-STORE trÃªn AWS" style="max-width:100%;height:auto;display:block;margin:1rem auto;border:1px solid #e5e7eb;border-radius:6px;" /></p>
<p style="text-align:center;"><em>Workflow tá»•ng thá»ƒ SUMMER-STORE trÃªn AWS</em></p>

#### Luá»“ng kiá»ƒm thá»­ chÃ­nh

1. Truy cáº­p website SUMMER-STORE qua S3 website endpoint.
2. ÄÄƒng nháº­p tÃ i khoáº£n user hoáº·c admin.
3. Frontend gá»i API backend thÃ´ng qua Elastic IP `13.223.11.215:8080`.
4. Backend EC2 xá»­ lÃ½ nghiá»‡p vá»¥ vÃ  Ä‘á»c/ghi dá»¯ liá»‡u vÃ o Amazon RDS SQL Server.
5. NgÆ°á»i dÃ¹ng táº¡o Ä‘Æ¡n hÃ ng vÃ  chá»n thanh toÃ¡n VNPay Sandbox.
6. Backend táº¡o URL thanh toÃ¡n vÃ  redirect ngÆ°á»i dÃ¹ng sang VNPay.
7. Sau khi thanh toÃ¡n, VNPay redirect/callback vá» backend.
8. Backend cáº­p nháº­t tráº¡ng thÃ¡i Ä‘Æ¡n hÃ ng trong database.

#### Káº¿t quáº£ Ä‘áº¡t Ä‘Æ°á»£c

- Website frontend truy cáº­p Ä‘Æ°á»£c tá»« Internet thÃ´ng qua Amazon S3.
- Backend Spring Boot cháº¡y á»•n Ä‘á»‹nh trÃªn Amazon EC2.
- API backend hoáº¡t Ä‘á»™ng qua Elastic IP vÃ  port 8080.
- Amazon RDS SQL Server lÆ°u trá»¯ Ä‘Æ°á»£c dá»¯ liá»‡u há»‡ thá»‘ng.
- áº¢nh sáº£n pháº©m Ä‘Æ°á»£c lÆ°u trá»¯ vÃ  hiá»ƒn thá»‹ tá»« Amazon S3.
- Chá»©c nÄƒng Ä‘Äƒng nháº­p, quáº£n lÃ½ sáº£n pháº©m, tá»“n kho, Ä‘Æ¡n hÃ ng vÃ  thanh toÃ¡n VNPay Sandbox Ä‘Æ°á»£c kiá»ƒm thá»­ á»Ÿ má»©c demo.

