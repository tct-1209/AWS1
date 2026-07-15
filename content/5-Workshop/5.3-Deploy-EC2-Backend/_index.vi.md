---
title: "Triá»ƒn khai Backend Spring Boot trÃªn Amazon EC2"
date: 2026-07-01
weight: 3
chapter: false
pre: " <b> 5.3. </b> "
---

# Triá»ƒn khai Backend Spring Boot trÃªn Amazon EC2

á»ž bÆ°á»›c nÃ y, backend Spring Boot cá»§a dá»± Ã¡n Ä‘Æ°á»£c triá»ƒn khai lÃªn Amazon EC2. EC2 Ä‘Ã³ng vai trÃ² lÃ  server cháº¡y á»©ng dá»¥ng backend, tiáº¿p nháº­n request tá»« frontend vÃ  káº¿t ná»‘i tá»›i database RDS.

#### 1. Khá»Ÿi táº¡o EC2 Instance

Khá»Ÿi táº¡o EC2 Instance Ä‘á»ƒ triá»ƒn khai backend Spring Boot cá»§a dá»± Ã¡n.

<p class="workshop-img"><img src="/AWS/images/5-Workshop/5.3-Deploy-EC2-Backend/5-3-01-ec2-instance.png" alt="Khá»Ÿi táº¡o EC2 Instance" style="max-width:100%;height:auto;display:block;margin:1rem auto;border:1px solid #e5e7eb;border-radius:6px;" /></p>
<p style="text-align:center;"><em>Khá»Ÿi táº¡o EC2 Instance</em></p>

#### 2. Cáº¥u hÃ¬nh Security Group cho EC2

Cáº¥u hÃ¬nh Security Group cho EC2. Port `22` dÃ¹ng Ä‘á»ƒ SSH, port `8080` dÃ¹ng Ä‘á»ƒ cháº¡y backend Spring Boot, port `80/443` dÃ¹ng cho HTTP vÃ  HTTPS náº¿u cáº§n má»Ÿ rá»™ng.

<p class="workshop-img"><img src="/AWS/images/5-Workshop/5.3-Deploy-EC2-Backend/5-3-02-security-group-ec2.png" alt="Cáº¥u hÃ¬nh Security Group cho EC2" style="max-width:100%;height:auto;display:block;margin:1rem auto;border:1px solid #e5e7eb;border-radius:6px;" /></p>
<p style="text-align:center;"><em>Cáº¥u hÃ¬nh Security Group cho EC2</em></p>

#### 3. Káº¿t ná»‘i EC2 báº±ng SSH

Káº¿t ná»‘i thÃ nh cÃ´ng vÃ o EC2 thÃ´ng qua SSH Ä‘á»ƒ cÃ i Ä‘áº·t mÃ´i trÆ°á»ng vÃ  triá»ƒn khai backend.

<p class="workshop-img"><img src="/AWS/images/5-Workshop/5.3-Deploy-EC2-Backend/5-3-03-ssh-connection.png" alt="Káº¿t ná»‘i SSH vÃ o EC2" style="max-width:100%;height:auto;display:block;margin:1rem auto;border:1px solid #e5e7eb;border-radius:6px;" /></p>
<p style="text-align:center;"><em>Káº¿t ná»‘i SSH vÃ o EC2</em></p>

VÃ­ dá»¥ lá»‡nh SSH:

```bash
ssh -i "backend.pem" ubuntu@13.223.11.215
```

#### 4. CÃ i Ä‘áº·t Java 17

CÃ i Ä‘áº·t Java 17 trÃªn EC2 Ä‘á»ƒ cháº¡y á»©ng dá»¥ng Spring Boot.

<p class="workshop-img"><img src="/AWS/images/5-Workshop/5.3-Deploy-EC2-Backend/5-3-04-java17.png" alt="Kiá»ƒm tra Java 17 trÃªn EC2" style="max-width:100%;height:auto;display:block;margin:1rem auto;border:1px solid #e5e7eb;border-radius:6px;" /></p>
<p style="text-align:center;"><em>Kiá»ƒm tra Java 17 trÃªn EC2</em></p>

#### 5. Build backend báº±ng Maven

Build backend Spring Boot thÃ nh cÃ´ng báº±ng Maven. File `.jar` Ä‘Æ°á»£c táº¡o trong thÆ° má»¥c `target` Ä‘á»ƒ chuáº©n bá»‹ triá»ƒn khai lÃªn Amazon EC2.

<p class="workshop-img"><img src="/AWS/images/5-Workshop/5.3-Deploy-EC2-Backend/5-3-05-maven-build.png" alt="Build backend báº±ng Maven" style="max-width:100%;height:auto;display:block;margin:1rem auto;border:1px solid #e5e7eb;border-radius:6px;" /></p>
<p style="text-align:center;"><em>Build backend báº±ng Maven</em></p>

VÃ­ dá»¥ lá»‡nh build:

```bash
./mvnw clean package -DskipTests
```

#### 6. Kiá»ƒm tra file `.jar` sau khi build

File `.jar` Ä‘Æ°á»£c táº¡o sau quÃ¡ trÃ¬nh build, Ä‘Ã¢y lÃ  artifact dÃ¹ng Ä‘á»ƒ deploy backend lÃªn EC2.

<p class="workshop-img"><img src="/AWS/images/5-Workshop/5.3-Deploy-EC2-Backend/5-3-06-target-jar.png" alt="File JAR trong thÆ° má»¥c target" style="max-width:100%;height:auto;display:block;margin:1rem auto;border:1px solid #e5e7eb;border-radius:6px;" /></p>
<p style="text-align:center;"><em>File JAR trong thÆ° má»¥c target</em></p>

#### 7. Upload file `.jar` lÃªn EC2

Upload file backend Spring Boot `.jar` tá»« mÃ¡y local lÃªn EC2 thÃ nh cÃ´ng báº±ng SCP. File Ä‘Æ°á»£c Ä‘á»•i tÃªn thÃ nh `app.jar` Ä‘á»ƒ dá»… quáº£n lÃ½ khi cháº¡y á»©ng dá»¥ng trÃªn server.

<p class="workshop-img"><img src="/AWS/images/5-Workshop/5.3-Deploy-EC2-Backend/5-3-07-upload-app-jar.png" alt="Upload app.jar lÃªn EC2" style="max-width:100%;height:auto;display:block;margin:1rem auto;border:1px solid #e5e7eb;border-radius:6px;" /></p>
<p style="text-align:center;"><em>Upload app.jar lÃªn EC2</em></p>

VÃ­ dá»¥ lá»‡nh upload:

```bash
scp -i "backend.pem" target/clothing-store-backend-0.0.1-SNAPSHOT.jar ubuntu@13.223.11.215:/home/ubuntu/clothing-store/app.jar
```

#### 8. Táº¡o file `.env` trÃªn EC2

Táº¡o file `.env` trÃªn EC2 Ä‘á»ƒ lÆ°u cÃ¡c biáº¿n mÃ´i trÆ°á»ng cáº§n thiáº¿t cho backend nhÆ° cáº¥u hÃ¬nh RDS, JWT, email, lÆ°u trá»¯ áº£nh vÃ  VNPay. File `.env` Ä‘Æ°á»£c Ä‘áº·t cÃ¹ng thÆ° má»¥c vá»›i `app.jar` Ä‘á»ƒ Spring Boot cÃ³ thá»ƒ Ä‘á»c cáº¥u hÃ¬nh khi khá»Ÿi Ä‘á»™ng.

<p class="workshop-img"><img src="/AWS/images/5-Workshop/5.3-Deploy-EC2-Backend/5-3-08-env-file.png" alt="Táº¡o file .env trÃªn EC2" style="max-width:100%;height:auto;display:block;margin:1rem auto;border:1px solid #e5e7eb;border-radius:6px;" /></p>
<p style="text-align:center;"><em>Táº¡o file .env trÃªn EC2</em></p>

