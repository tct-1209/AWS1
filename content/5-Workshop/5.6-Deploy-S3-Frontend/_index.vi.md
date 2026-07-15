---
title: "Deploy frontend React vá»›i Amazon S3 Static Website Hosting"
date: 2026-07-01
weight: 6
chapter: false
pre: " <b> 5.6. </b> "
---

# Deploy frontend React vá»›i Amazon S3 Static Website Hosting

Frontend React/Vite Ä‘Æ°á»£c build thÃ nh cÃ¡c file static vÃ  upload lÃªn Amazon S3. S3 Static Website Hosting giÃºp website cÃ³ thá»ƒ truy cáº­p thÃ´ng qua S3 website endpoint.

#### 1. Build frontend React/Vite

Build frontend React thÃ nh cÃ¡c file static Ä‘á»ƒ chuáº©n bá»‹ triá»ƒn khai lÃªn Amazon S3.

<p class="workshop-img"><img src="/AWS/images/5-Workshop/5.6-Deploy-S3-Frontend/5-6-01-frontend-source.png" alt="ThÆ° má»¥c frontend trÆ°á»›c khi build" style="max-width:100%;height:auto;display:block;margin:1rem auto;border:1px solid #e5e7eb;border-radius:6px;" /></p>
<p style="text-align:center;"><em>ThÆ° má»¥c frontend trÆ°á»›c khi build</em></p>

VÃ­ dá»¥ lá»‡nh build:

```bash
npm install
npm run build
```

#### 2. Táº¡o S3 Bucket cho frontend

Táº¡o S3 Bucket riÃªng Ä‘á»ƒ lÆ°u trá»¯ cÃ¡c file static cá»§a frontend React sau khi build.

<p class="workshop-img"><img src="/AWS/images/5-Workshop/5.6-Deploy-S3-Frontend/5-6-02-s3-frontend-bucket.png" alt="Táº¡o S3 frontend bucket" style="max-width:100%;height:auto;display:block;margin:1rem auto;border:1px solid #e5e7eb;border-radius:6px;" /></p>
<p style="text-align:center;"><em>Táº¡o S3 frontend bucket</em></p>

Bucket frontend cá»§a dá»± Ã¡n:

```text
clothing-store-frontend-dien0311
```

#### 3. Upload file static lÃªn S3

Upload toÃ n bá»™ file static sau khi build frontend React lÃªn Amazon S3. CÃ¡c thÆ° má»¥c `assets` vÃ  `images` Ä‘Æ°á»£c giá»¯ nguyÃªn Ä‘á»ƒ website cÃ³ thá»ƒ load Ä‘Ãºng JavaScript, CSS vÃ  hÃ¬nh áº£nh.

<p class="workshop-img"><img src="/AWS/images/5-Workshop/5.6-Deploy-S3-Frontend/5-6-03-upload-static-files.png" alt="Upload file static frontend lÃªn S3" style="max-width:100%;height:auto;display:block;margin:1rem auto;border:1px solid #e5e7eb;border-radius:6px;" /></p>
<p style="text-align:center;"><em>Upload file static frontend lÃªn S3</em></p>

#### 4. Báº­t Static Website Hosting

Báº­t Static Website Hosting cho S3 Bucket Ä‘á»ƒ triá»ƒn khai frontend React dÆ°á»›i dáº¡ng website tÄ©nh. File `index.html` Ä‘Æ°á»£c sá»­ dá»¥ng lÃ m trang chÃ­nh cá»§a á»©ng dá»¥ng.

<p class="workshop-img"><img src="/AWS/images/5-Workshop/5.6-Deploy-S3-Frontend/5-6-04-static-website-hosting.png" alt="Báº­t Static Website Hosting cho S3" style="max-width:100%;height:auto;display:block;margin:1rem auto;border:1px solid #e5e7eb;border-radius:6px;" /></p>
<p style="text-align:center;"><em>Báº­t Static Website Hosting cho S3</em></p>

Cáº¥u hÃ¬nh cÆ¡ báº£n:

```text
Index document: index.html
Error document: index.html
```

#### 5. Kiá»ƒm tra website sau khi deploy

Frontend React Ä‘Ã£ Ä‘Æ°á»£c build vÃ  triá»ƒn khai thÃ nh cÃ´ng lÃªn Amazon S3 Static Website Hosting. Website cÃ³ thá»ƒ truy cáº­p thÃ´ng qua S3 website endpoint vÃ  táº£i Ä‘Æ°á»£c Ä‘áº§y Ä‘á»§ file HTML, CSS, JavaScript, hÃ¬nh áº£nh.

<p class="workshop-img"><img src="/AWS/images/5-Workshop/5.6-Deploy-S3-Frontend/5-6-05-frontend-s3-success.png" alt="Frontend SUMMER-STORE cháº¡y trÃªn S3" style="max-width:100%;height:auto;display:block;margin:1rem auto;border:1px solid #e5e7eb;border-radius:6px;" /></p>
<p style="text-align:center;"><em>Frontend SUMMER-STORE cháº¡y trÃªn S3</em></p>

{{% notice note %}}
Trong pháº¡m vi dá»± Ã¡n hiá»‡n táº¡i, frontend Ä‘Æ°á»£c triá»ƒn khai trá»±c tiáº¿p báº±ng S3 Static Website Hosting. CloudFront vÃ  Route 53 cÃ³ thá»ƒ Ä‘Æ°á»£c bá»• sung sau náº¿u cáº§n domain riÃªng, HTTPS vÃ  CDN.
{{% /notice %}}

