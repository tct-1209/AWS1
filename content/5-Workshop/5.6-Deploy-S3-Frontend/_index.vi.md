---
title: "Deploy frontend React với Amazon S3 Static Website Hosting"
date: 2026-07-01
weight: 6
chapter: false
pre: " <b> 5.6. </b> "
---

# Deploy frontend React với Amazon S3 Static Website Hosting

Frontend React/Vite được build thành các file static và upload lên Amazon S3. S3 Static Website Hosting giúp website có thể truy cập thông qua S3 website endpoint.

#### 1. Build frontend React/Vite

Build frontend React thành các file static để chuẩn bị triển khai lên Amazon S3.

<p class="workshop-img"><img src="/AWS/images/5-Workshop/5.6-Deploy-S3-Frontend/5-6-01-frontend-source.png" alt="Thư mục frontend trước khi build" style="max-width:100%;height:auto;display:block;margin:1rem auto;border:1px solid #e5e7eb;border-radius:6px;" /></p>
<p style="text-align:center;"><em>Thư mục frontend trước khi build</em></p>

Ví dụ lệnh build:

```bash
npm install
npm run build
```

#### 2. Tạo S3 Bucket cho frontend

Tạo S3 Bucket riêng để lưu trữ các file static của frontend React sau khi build.

<p class="workshop-img"><img src="/AWS/images/5-Workshop/5.6-Deploy-S3-Frontend/5-6-02-s3-frontend-bucket.png" alt="Tạo S3 frontend bucket" style="max-width:100%;height:auto;display:block;margin:1rem auto;border:1px solid #e5e7eb;border-radius:6px;" /></p>
<p style="text-align:center;"><em>Tạo S3 frontend bucket</em></p>

Bucket frontend của dự án:

```text
clothing-store-frontend-dien0311
```

#### 3. Upload file static lên S3

Upload toàn bộ file static sau khi build frontend React lên Amazon S3. Các thư mục `assets` và `images` được giữ nguyên để website có thể load đúng JavaScript, CSS và hình ảnh.

<p class="workshop-img"><img src="/AWS/images/5-Workshop/5.6-Deploy-S3-Frontend/5-6-03-upload-static-files.png" alt="Upload file static frontend lên S3" style="max-width:100%;height:auto;display:block;margin:1rem auto;border:1px solid #e5e7eb;border-radius:6px;" /></p>
<p style="text-align:center;"><em>Upload file static frontend lên S3</em></p>

#### 4. Bật Static Website Hosting

Bật Static Website Hosting cho S3 Bucket để triển khai frontend React dưới dạng website tĩnh. File `index.html` được sử dụng làm trang chính của ứng dụng.

<p class="workshop-img"><img src="/AWS/images/5-Workshop/5.6-Deploy-S3-Frontend/5-6-04-static-website-hosting.png" alt="Bật Static Website Hosting cho S3" style="max-width:100%;height:auto;display:block;margin:1rem auto;border:1px solid #e5e7eb;border-radius:6px;" /></p>
<p style="text-align:center;"><em>Bật Static Website Hosting cho S3</em></p>

Cấu hình cơ bản:

```text
Index document: index.html
Error document: index.html
```

#### 5. Kiểm tra website sau khi deploy

Frontend React đã được build và triển khai thành công lên Amazon S3 Static Website Hosting. Website có thể truy cập thông qua S3 website endpoint và tải được đầy đủ file HTML, CSS, JavaScript, hình ảnh.

<p class="workshop-img"><img src="/AWS/images/5-Workshop/5.6-Deploy-S3-Frontend/5-6-05-frontend-s3-success.png" alt="Frontend SUMMER-STORE chạy trên S3" style="max-width:100%;height:auto;display:block;margin:1rem auto;border:1px solid #e5e7eb;border-radius:6px;" /></p>
<p style="text-align:center;"><em>Frontend SUMMER-STORE chạy trên S3</em></p>

{{% notice note %}}
Trong phạm vi dự án hiện tại, frontend được triển khai trực tiếp bằng S3 Static Website Hosting. CloudFront và Route 53 có thể được bổ sung sau nếu cần domain riêng, HTTPS và CDN.
{{% /notice %}}


