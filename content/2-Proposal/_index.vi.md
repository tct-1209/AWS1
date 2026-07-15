---
title: "Báº£n Ä‘á» xuáº¥t"
date: 2026-07-01
weight: 2
chapter: false
pre: " <b> 2. </b> "
---

# Báº£n Ä‘á» xuáº¥t triá»ƒn khai dá»± Ã¡n SUMMER-STORE trÃªn AWS

## 1. TÃªn Ä‘á» tÃ i

**Triá»ƒn khai website thÆ°Æ¡ng máº¡i Ä‘iá»‡n tá»­ SUMMER-STORE trÃªn ná»n táº£ng AWS**

Dá»± Ã¡n táº­p trung vÃ o viá»‡c Ä‘Æ°a há»‡ thá»‘ng website bÃ¡n quáº§n Ã¡o **SUMMER-STORE** tá»« mÃ´i trÆ°á»ng local lÃªn AWS. Há»‡ thá»‘ng bao gá»“m frontend React/Vite, backend Spring Boot, database SQL Server vÃ  chá»©c nÄƒng thanh toÃ¡n thá»­ nghiá»‡m qua VNPay Sandbox.

## 2. LÃ½ do chá»n Ä‘á» tÃ i

Trong thá»±c táº¿, má»™t website thÆ°Æ¡ng máº¡i Ä‘iá»‡n tá»­ khÃ´ng chá»‰ cáº§n cháº¡y Ä‘Æ°á»£c trÃªn mÃ¡y local mÃ  cÃ²n cáº§n cÃ³ kháº£ nÄƒng truy cáº­p qua Internet, lÆ°u trá»¯ dá»¯ liá»‡u táº­p trung, xá»­ lÃ½ API á»•n Ä‘á»‹nh vÃ  dá»… theo dÃµi chi phÃ­ váº­n hÃ nh. VÃ¬ váº­y, Ä‘á» tÃ i nÃ y Ä‘Æ°á»£c lá»±a chá»n nháº±m thá»±c hÃ nh quy trÃ¬nh triá»ƒn khai má»™t há»‡ thá»‘ng fullstack lÃªn cloud thÃ´ng qua cÃ¡c dá»‹ch vá»¥ AWS cÆ¡ báº£n.

Viá»‡c triá»ƒn khai SUMMER-STORE trÃªn AWS giÃºp sinh viÃªn hiá»ƒu rÃµ hÆ¡n cÃ¡ch káº¿t há»£p **Amazon S3**, **Amazon EC2**, **Amazon RDS**, **Elastic IP**, **IAM**, **AWS CLI**, **CloudWatch** vÃ  **AWS Budgets** trong má»™t bÃ i toÃ¡n gáº§n vá»›i thá»±c táº¿.

## 3. Má»¥c tiÃªu Ä‘á» tÃ i

- Triá»ƒn khai frontend React/Vite báº±ng **Amazon S3 Static Website Hosting**.
- Triá»ƒn khai backend Spring Boot trÃªn **Amazon EC2**.
- Sá»­ dá»¥ng **Amazon RDS for SQL Server** Ä‘á»ƒ lÆ°u dá»¯ liá»‡u há»‡ thá»‘ng.
- Cáº¥u hÃ¬nh **Elastic IP** Ä‘á»ƒ cá»‘ Ä‘á»‹nh Ä‘á»‹a chá»‰ truy cáº­p API backend.
- Cáº¥u hÃ¬nh **Security Group** cho SSH, API backend vÃ  káº¿t ná»‘i database.
- LÆ°u trá»¯ áº£nh sáº£n pháº©m báº±ng **Amazon S3**.
- Kiá»ƒm thá»­ cÃ¡c chá»©c nÄƒng chÃ­nh: Ä‘Äƒng nháº­p, quáº£n lÃ½ sáº£n pháº©m, tá»“n kho, Ä‘Æ¡n hÃ ng vÃ  thanh toÃ¡n VNPay Sandbox.
- Theo dÃµi hoáº¡t Ä‘á»™ng vÃ  chi phÃ­ báº±ng **CloudWatch**, **AWS Budgets** vÃ  **Billing**.

## 4. Pháº¡m vi thá»±c hiá»‡n

Pháº¡m vi Ä‘á» tÃ i táº­p trung vÃ o triá»ƒn khai há»‡ thá»‘ng á»Ÿ má»©c demo/thá»±c táº­p. CÃ¡c chá»©c nÄƒng chÃ­nh gá»“m Ä‘Äƒng kÃ½, Ä‘Äƒng nháº­p, hiá»ƒn thá»‹ sáº£n pháº©m, quáº£n lÃ½ sáº£n pháº©m, quáº£n lÃ½ biáº¿n thá»ƒ, quáº£n lÃ½ tá»“n kho, quáº£n lÃ½ Ä‘Æ¡n hÃ ng vÃ  thanh toÃ¡n thá»­ nghiá»‡m báº±ng VNPay Sandbox.

Äá» tÃ i chÆ°a triá»ƒn khai cÃ¡c thÃ nh pháº§n nÃ¢ng cao nhÆ° Load Balancer, Auto Scaling, Route 53, CloudFront CDN hoáº·c CI/CD tá»± Ä‘á»™ng hoÃ n chá»‰nh. Nhá»¯ng thÃ nh pháº§n nÃ y cÃ³ thá»ƒ Ä‘Æ°á»£c bá»• sung trong giai Ä‘oáº¡n má»Ÿ rá»™ng sau.

## 5. Kiáº¿n trÃºc Ä‘á» xuáº¥t

NgÆ°á»i dÃ¹ng hoáº·c admin truy cáº­p website thÃ´ng qua trÃ¬nh duyá»‡t. Frontend Ä‘Æ°á»£c host trÃªn **Amazon S3 Static Website Hosting**. Sau khi táº£i giao diá»‡n vá» trÃ¬nh duyá»‡t, á»©ng dá»¥ng React/Vite gá»i API tá»›i backend thÃ´ng qua **Elastic IP** cá»§a EC2. Backend Spring Boot cháº¡y trÃªn **Amazon EC2**, xá»­ lÃ½ nghiá»‡p vá»¥ vÃ  káº¿t ná»‘i tá»›i **Amazon RDS SQL Server** Ä‘á»ƒ Ä‘á»c/ghi dá»¯ liá»‡u. Vá»›i chá»©c nÄƒng thanh toÃ¡n, backend táº¡o URL thanh toÃ¡n VNPay Sandbox vÃ  nháº­n redirect/callback Ä‘á»ƒ cáº­p nháº­t tráº¡ng thÃ¡i Ä‘Æ¡n hÃ ng.

<p class="workshop-img"><img src="/AWS/images/2-Proposal/summer-store-workflow.png" alt="Workflow triá»ƒn khai SUMMER-STORE trÃªn AWS" style="max-width:100%;height:auto;display:block;margin:1rem auto;border:1px solid #e5e7eb;border-radius:6px;" /></p>
<p style="text-align:center;"><em>Workflow triá»ƒn khai SUMMER-STORE trÃªn AWS</em></p>

## 6. CÃ¡c dá»‹ch vá»¥ AWS sá»­ dá»¥ng

| Dá»‹ch vá»¥ | Vai trÃ² trong dá»± Ã¡n |
|---|---|
| **Amazon S3 Static Website Hosting** | Host frontend React/Vite gá»“m `index.html`, JavaScript, CSS vÃ  tÃ i nguyÃªn tÄ©nh. |
| **Amazon S3 Product Images Bucket** | LÆ°u trá»¯ áº£nh sáº£n pháº©m vÃ  media cá»§a há»‡ thá»‘ng. |
| **Amazon EC2** | Cháº¡y backend Spring Boot báº±ng file `app.jar`. |
| **Elastic IP** | Cá»‘ Ä‘á»‹nh Ä‘á»‹a chá»‰ backend API, vÃ­ dá»¥ `13.223.11.215:8080`. |
| **Amazon RDS for SQL Server** | LÆ°u trá»¯ dá»¯ liá»‡u ngÆ°á»i dÃ¹ng, sáº£n pháº©m, giá» hÃ ng, Ä‘Æ¡n hÃ ng vÃ  biáº¿n thá»ƒ sáº£n pháº©m. |
| **Security Group** | Kiá»ƒm soÃ¡t truy cáº­p port `22`, `8080`, `80/443` vÃ  `1433`. |
| **AWS IAM** | Quáº£n lÃ½ user, quyá»n truy cáº­p vÃ  access key cho AWS CLI. |
| **AWS CLI** | Há»— trá»£ start/stop EC2, kiá»ƒm tra tráº¡ng thÃ¡i tÃ i nguyÃªn vÃ  thao tÃ¡c vá»›i AWS tá»« mÃ¡y local. |
| **Amazon CloudWatch** | Theo dÃµi log vÃ  tráº¡ng thÃ¡i váº­n hÃ nh cÆ¡ báº£n. |
| **AWS Budgets / Billing** | Theo dÃµi credit vÃ  chi phÃ­ sá»­ dá»¥ng AWS. |

## 7. Thiáº¿t káº¿ thÃ nh pháº§n

### 7.1 Frontend

Frontend Ä‘Æ°á»£c phÃ¡t triá»ƒn báº±ng React/Vite. Sau khi build, cÃ¡c file static trong thÆ° má»¥c `dist` Ä‘Æ°á»£c upload lÃªn S3 bucket frontend Ä‘á»ƒ ngÆ°á»i dÃ¹ng cÃ³ thá»ƒ truy cáº­p website qua S3 website endpoint.

<p class="workshop-img"><img src="/AWS/images/2-Proposal/s3-frontend-success.png" alt="Frontend triá»ƒn khai trÃªn Amazon S3" style="max-width:100%;height:auto;display:block;margin:1rem auto;border:1px solid #e5e7eb;border-radius:6px;" /></p>
<p style="text-align:center;"><em>Frontend SUMMER-STORE sau khi triá»ƒn khai lÃªn Amazon S3</em></p>

### 7.2 Backend

Backend Ä‘Æ°á»£c phÃ¡t triá»ƒn báº±ng Spring Boot. á»¨ng dá»¥ng Ä‘Æ°á»£c build thÃ nh file `.jar`, upload lÃªn EC2 vÃ  cháº¡y báº±ng Java 17. Backend tiáº¿p nháº­n request tá»« frontend, xá»­ lÃ½ nghiá»‡p vá»¥ vÃ  tráº£ dá»¯ liá»‡u API cho website.

<p class="workshop-img"><img src="/AWS/images/2-Proposal/ec2-backend-instance.png" alt="Amazon EC2 cháº¡y backend Spring Boot" style="max-width:100%;height:auto;display:block;margin:1rem auto;border:1px solid #e5e7eb;border-radius:6px;" /></p>
<p style="text-align:center;"><em>Amazon EC2 Ä‘Æ°á»£c sá»­ dá»¥ng Ä‘á»ƒ triá»ƒn khai backend Spring Boot</em></p>

### 7.3 Database

Database sá»­ dá»¥ng Amazon RDS for SQL Server. Backend káº¿t ná»‘i Ä‘áº¿n RDS thÃ´ng qua JDBC Ä‘á»ƒ lÆ°u trá»¯ vÃ  truy váº¥n dá»¯ liá»‡u nhÆ° tÃ i khoáº£n ngÆ°á»i dÃ¹ng, sáº£n pháº©m, biáº¿n thá»ƒ sáº£n pháº©m, giá» hÃ ng vÃ  Ä‘Æ¡n hÃ ng.

<p class="workshop-img"><img src="/AWS/images/2-Proposal/rds-sqlserver-available.png" alt="Amazon RDS SQL Server" style="max-width:100%;height:auto;display:block;margin:1rem auto;border:1px solid #e5e7eb;border-radius:6px;" /></p>
<p style="text-align:center;"><em>Amazon RDS SQL Server á»Ÿ tráº¡ng thÃ¡i Available</em></p>

### 7.4 Thanh toÃ¡n

VNPay Sandbox lÃ  dá»‹ch vá»¥ thanh toÃ¡n bÃªn ngoÃ i AWS. Backend táº¡o payment URL, chuyá»ƒn ngÆ°á»i dÃ¹ng sang trang thanh toÃ¡n VNPay vÃ  nháº­n káº¿t quáº£ redirect/callback Ä‘á»ƒ cáº­p nháº­t tráº¡ng thÃ¡i Ä‘Æ¡n hÃ ng trong database.

## 8. Káº¿ hoáº¡ch triá»ƒn khai

| Giai Ä‘oáº¡n | Ná»™i dung thá»±c hiá»‡n |
|---|---|
| Giai Ä‘oáº¡n 1 | Chuáº©n bá»‹ mÃ£ nguá»“n frontend, backend, tÃ i khoáº£n AWS, IAM user vÃ  AWS CLI. |
| Giai Ä‘oáº¡n 2 | Táº¡o EC2, cáº¥u hÃ¬nh Security Group, cÃ i Java 17 vÃ  deploy backend Spring Boot. |
| Giai Ä‘oáº¡n 3 | Táº¡o Amazon RDS SQL Server, táº¡o database `clothing_store_backend` vÃ  cáº­p nháº­t file `.env`. |
| Giai Ä‘oáº¡n 4 | Táº¡o S3 bucket lÆ°u áº£nh sáº£n pháº©m vÃ  cáº¥u hÃ¬nh bucket policy phÃ¹ há»£p. |
| Giai Ä‘oáº¡n 5 | Build frontend React/Vite, upload file static lÃªn S3 vÃ  báº­t Static Website Hosting. |
| Giai Ä‘oáº¡n 6 | Gáº¯n Elastic IP, kiá»ƒm thá»­ API, Ä‘Äƒng nháº­p, quáº£n lÃ½ sáº£n pháº©m, Ä‘Æ¡n hÃ ng vÃ  VNPay Sandbox. |
| Giai Ä‘oáº¡n 7 | Theo dÃµi váº­n hÃ nh, kiá»ƒm tra chi phÃ­ vÃ  dá»n dáº¹p tÃ i nguyÃªn khÃ´ng cáº§n thiáº¿t. |

## 9. Káº¿t quáº£ mong Ä‘á»£i

Sau khi hoÃ n thÃ nh, há»‡ thá»‘ng SUMMER-STORE cÃ³ thá»ƒ hoáº¡t Ä‘á»™ng trÃªn mÃ´i trÆ°á»ng AWS vá»›i cÃ¡c káº¿t quáº£ sau:

- NgÆ°á»i dÃ¹ng truy cáº­p Ä‘Æ°á»£c frontend thÃ´ng qua S3 website endpoint.
- Frontend gá»i Ä‘Æ°á»£c API backend thÃ´ng qua Elastic IP.
- Backend Spring Boot cháº¡y á»•n Ä‘á»‹nh trÃªn EC2 báº±ng `systemd service`.
- Dá»¯ liá»‡u Ä‘Æ°á»£c lÆ°u trá»¯ vÃ  truy váº¥n tá»« Amazon RDS SQL Server.
- Admin cÃ³ thá»ƒ quáº£n lÃ½ sáº£n pháº©m, tá»“n kho vÃ  Ä‘Æ¡n hÃ ng.
- NgÆ°á»i dÃ¹ng cÃ³ thá»ƒ Ä‘áº·t hÃ ng vÃ  thanh toÃ¡n thá»­ nghiá»‡m qua VNPay Sandbox.
- NgÆ°á»i thá»±c hiá»‡n náº¯m Ä‘Æ°á»£c quy trÃ¬nh triá»ƒn khai website fullstack lÃªn AWS vÃ  cÃ¡ch theo dÃµi chi phÃ­ cloud.

## 10. Rá»§i ro vÃ  hÆ°á»›ng xá»­ lÃ½

| Rá»§i ro | HÆ°á»›ng xá»­ lÃ½ |
|---|---|
| Backend khÃ´ng truy cáº­p Ä‘Æ°á»£c tá»« frontend | Kiá»ƒm tra Security Group, port `8080`, Elastic IP vÃ  CORS. |
| EC2 khÃ´ng káº¿t ná»‘i Ä‘Æ°á»£c RDS | Kiá»ƒm tra endpoint RDS, port `1433`, Security Group vÃ  thÃ´ng tin `.env`. |
| áº¢nh sáº£n pháº©m khÃ´ng hiá»ƒn thá»‹ | Kiá»ƒm tra S3 bucket policy, object URL vÃ  quyá»n public read náº¿u cáº§n. |
| VNPay Sandbox lá»—i callback | Kiá»ƒm tra `returnUrl`, mÃ£ cáº¥u hÃ¬nh VNPay vÃ  chá»¯ kÃ½ báº£o máº­t. |
| Chi phÃ­ AWS vÆ°á»£t dá»± kiáº¿n | Theo dÃµi Billing/Budgets, stop EC2/RDS khi khÃ´ng sá»­ dá»¥ng. |

## 11. HÆ°á»›ng má»Ÿ rá»™ng

Trong tÆ°Æ¡ng lai, há»‡ thá»‘ng cÃ³ thá»ƒ Ä‘Æ°á»£c má»Ÿ rá»™ng báº±ng cÃ¡ch sá»­ dá»¥ng **CloudFront** Ä‘á»ƒ tÄƒng tá»‘c frontend, **Route 53** Ä‘á»ƒ gáº¯n tÃªn miá»n riÃªng, **Application Load Balancer** vÃ  **Auto Scaling** Ä‘á»ƒ tÄƒng Ä‘á»™ sáºµn sÃ ng cho backend, cÅ©ng nhÆ° triá»ƒn khai CI/CD Ä‘á»ƒ tá»± Ä‘á»™ng build vÃ  deploy mÃ£ nguá»“n.

