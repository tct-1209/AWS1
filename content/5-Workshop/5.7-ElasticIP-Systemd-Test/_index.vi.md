---
title: "Kiá»ƒm thá»­ backend, Elastic IP vÃ  API"
date: 2026-07-01
weight: 7
chapter: false
pre: " <b> 5.7. </b> "
---

# Kiá»ƒm thá»­ backend, Elastic IP vÃ  API

Sau khi triá»ƒn khai backend lÃªn EC2 vÃ  cáº¥u hÃ¬nh frontend gá»i API qua Elastic IP, cáº§n kiá»ƒm tra port 8080, endpoint API vÃ  tráº¡ng thÃ¡i cháº¡y cá»§a á»©ng dá»¥ng backend.

#### 1. Kiá»ƒm tra port 8080 tá»« mÃ¡y local

Kiá»ƒm tra káº¿t ná»‘i tá»« mÃ¡y local tá»›i backend EC2 qua port `8080`. Káº¿t quáº£ `TcpTestSucceeded: True` xÃ¡c nháº­n Security Group vÃ  network Ä‘Ã£ cho phÃ©p truy cáº­p API tá»« bÃªn ngoÃ i.

<p class="workshop-img"><img src="/AWS/images/5-Workshop/5.7-ElasticIP-Systemd-Test/5-7-01-test-port-8080.png" alt="Test port 8080 tá»« mÃ¡y local" style="max-width:100%;height:auto;display:block;margin:1rem auto;border:1px solid #e5e7eb;border-radius:6px;" /></p>
<p style="text-align:center;"><em>Test port 8080 tá»« mÃ¡y local</em></p>

VÃ­ dá»¥ lá»‡nh PowerShell:

```powershell
Test-NetConnection 13.223.11.215 -Port 8080
```

#### 2. Kiá»ƒm tra endpoint `/v3/api-docs`

Endpoint `/v3/api-docs` tráº£ vá» tÃ i liá»‡u OpenAPI JSON, xÃ¡c nháº­n backend Spring Boot Ä‘Ã£ public API thÃ nh cÃ´ng trÃªn EC2 thÃ´ng qua port 8080.

<p class="workshop-img"><img src="/AWS/images/5-Workshop/5.7-ElasticIP-Systemd-Test/5-7-02-api-docs-browser.png" alt="Kiá»ƒm tra api-docs trÃªn trÃ¬nh duyá»‡t" style="max-width:100%;height:auto;display:block;margin:1rem auto;border:1px solid #e5e7eb;border-radius:6px;" /></p>
<p style="text-align:center;"><em>Kiá»ƒm tra api-docs trÃªn trÃ¬nh duyá»‡t</em></p>

#### 3. Kiá»ƒm tra trá»±c tiáº¿p trÃªn EC2

Kiá»ƒm tra trá»±c tiáº¿p trÃªn EC2 cho tháº¥y backend Ä‘ang cháº¡y á»•n Ä‘á»‹nh á»Ÿ port `8080` vÃ  endpoint `/v3/api-docs` tráº£ vá» HTTP 200.

<p class="workshop-img"><img src="/AWS/images/5-Workshop/5.7-ElasticIP-Systemd-Test/5-7-03-curl-api-docs.png" alt="curl localhost api-docs trÃªn EC2" style="max-width:100%;height:auto;display:block;margin:1rem auto;border:1px solid #e5e7eb;border-radius:6px;" /></p>
<p style="text-align:center;"><em>curl localhost api-docs trÃªn EC2</em></p>

VÃ­ dá»¥ lá»‡nh kiá»ƒm tra:

```bash
curl -I http://localhost:8080/v3/api-docs
```

#### 4. Kiá»ƒm tra file triá»ƒn khai trÃªn EC2

File `app.jar` lÃ  backend Spring Boot Ä‘Ã£ Ä‘Æ°á»£c build vÃ  upload lÃªn EC2. File `.env` lÆ°u cÃ¡c biáº¿n mÃ´i trÆ°á»ng nhÆ° cáº¥u hÃ¬nh RDS, JWT, email, lÆ°u trá»¯ áº£nh vÃ  VNPay.

<p class="workshop-img"><img src="/AWS/images/5-Workshop/5.7-ElasticIP-Systemd-Test/5-7-04-app-env-final.png" alt="Kiá»ƒm tra app.jar vÃ  .env trÃªn EC2" style="max-width:100%;height:auto;display:block;margin:1rem auto;border:1px solid #e5e7eb;border-radius:6px;" /></p>
<p style="text-align:center;"><em>Kiá»ƒm tra app.jar vÃ  .env trÃªn EC2</em></p>

#### 5. Cháº¡y backend báº±ng systemd service

Äá»ƒ backend luÃ´n cháº¡y sau khi Ä‘Ã³ng SSH/PowerShell, táº¡o service `clothing-store-backend` báº±ng systemd.

Má»™t sá»‘ lá»‡nh kiá»ƒm tra service:

```bash
sudo systemctl restart clothing-store-backend
sudo systemctl status clothing-store-backend --no-pager
```

Khi service hiá»ƒn thá»‹ `active (running)`, backend cÃ³ thá»ƒ tiáº¿p tá»¥c hoáº¡t Ä‘á»™ng ká»ƒ cáº£ khi Ä‘Ã³ng terminal SSH.

