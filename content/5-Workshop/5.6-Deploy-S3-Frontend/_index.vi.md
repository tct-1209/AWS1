---
title: "Deploy frontend React v?i Amazon S3 Static Website Hosting"
date: 2026-07-01
weight: 6
chapter: false
pre: " <b> 5.6. </b> "
---

# Deploy frontend React v?i Amazon S3 Static Website Hosting

Frontend React/Vite du?c build th�nh c�c file static v� upload l�n Amazon S3. S3 Static Website Hosting gi�p website c� th? truy c?p th�ng qua S3 website endpoint.

#### 1. Build frontend React/Vite

Build frontend React th�nh c�c file static d? chu?n b? tri?n khai l�n Amazon S3.

<p class="workshop-img"><img src="/AWS/images/5-Workshop/5.6-Deploy-S3-Frontend/5-6-01-frontend-source.png" alt="Thu m?c frontend tru?c khi build" style="max-width:100%;height:auto;display:block;margin:1rem auto;border:1px solid #e5e7eb;border-radius:6px;" /></p>
<p style="text-align:center;"><em>Thu m?c frontend tru?c khi build</em></p>

V� d? l?nh build:

```bash
npm install
npm run build
```

#### 2. T?o S3 Bucket cho frontend

T?o S3 Bucket ri�ng d? luu tr? c�c file static c?a frontend React sau khi build.

<p class="workshop-img"><img src="/AWS/images/5-Workshop/5.6-Deploy-S3-Frontend/5-6-02-s3-frontend-bucket.png" alt="T?o S3 frontend bucket" style="max-width:100%;height:auto;display:block;margin:1rem auto;border:1px solid #e5e7eb;border-radius:6px;" /></p>
<p style="text-align:center;"><em>T?o S3 frontend bucket</em></p>

Bucket frontend c?a d? �n:

```text
clothing-store-frontend-dien0311
```

#### 3. Upload file static l�n S3

Upload to�n b? file static sau khi build frontend React l�n Amazon S3. C�c thu m?c `assets` v� `images` du?c gi? nguy�n d? website c� th? load d�ng JavaScript, CSS v� h�nh ?nh.

<p class="workshop-img"><img src="/AWS/images/5-Workshop/5.6-Deploy-S3-Frontend/5-6-03-upload-static-files.png" alt="Upload file static frontend l�n S3" style="max-width:100%;height:auto;display:block;margin:1rem auto;border:1px solid #e5e7eb;border-radius:6px;" /></p>
<p style="text-align:center;"><em>Upload file static frontend l�n S3</em></p>

#### 4. B?t Static Website Hosting

B?t Static Website Hosting cho S3 Bucket d? tri?n khai frontend React du?i d?ng website tinh. File `index.html` du?c s? d?ng l�m trang ch�nh c?a ?ng d?ng.

<p class="workshop-img"><img src="/AWS/images/5-Workshop/5.6-Deploy-S3-Frontend/5-6-04-static-website-hosting.png" alt="B?t Static Website Hosting cho S3" style="max-width:100%;height:auto;display:block;margin:1rem auto;border:1px solid #e5e7eb;border-radius:6px;" /></p>
<p style="text-align:center;"><em>B?t Static Website Hosting cho S3</em></p>

C?u h�nh co b?n:

```text
Index document: index.html
Error document: index.html
```

#### 5. Ki?m tra website sau khi deploy

Frontend React d� du?c build v� tri?n khai th�nh c�ng l�n Amazon S3 Static Website Hosting. Website c� th? truy c?p th�ng qua S3 website endpoint v� t?i du?c d?y d? file HTML, CSS, JavaScript, h�nh ?nh.

<p class="workshop-img"><img src="/AWS/images/5-Workshop/5.6-Deploy-S3-Frontend/5-6-05-frontend-s3-success.png" alt="Frontend SUMMER-STORE ch?y tr�n S3" style="max-width:100%;height:auto;display:block;margin:1rem auto;border:1px solid #e5e7eb;border-radius:6px;" /></p>
<p style="text-align:center;"><em>Frontend SUMMER-STORE ch?y tr�n S3</em></p>

{{% notice note %}}
Trong ph?m vi d? �n hi?n t?i, frontend du?c tri?n khai tr?c ti?p b?ng S3 Static Website Hosting. CloudFront v� Route 53 c� th? du?c b? sung sau n?u c?n domain ri�ng, HTTPS v� CDN.
{{% /notice %}}








