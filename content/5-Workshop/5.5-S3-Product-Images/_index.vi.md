---
title: "Lưu trữ ảnh sản phẩm bằng Amazon S3"
date: 2026-07-01
weight: 5
chapter: false
pre: " <b> 5.5. </b> "
---

# Lưu trữ ảnh sản phẩm bằng Amazon S3

Amazon S3 được sử dụng để lưu trữ ảnh sản phẩm và các file media cho dự án SUMMER-STORE. Việc tách ảnh ra khỏi backend giúp hệ thống dễ quản lý file, giảm tải cho EC2 và thuận tiện khi frontend cần hiển thị ảnh.

#### 1. Tạo bucket lưu ảnh sản phẩm

Tạo thành công Amazon S3 Bucket `clothing-store-images-dien0311` để lưu trữ ảnh sản phẩm và các file media cho dự án SUMMER-STORE.

<p class="workshop-img"><img src="/AWS/images/5-Workshop/5.5-S3-Product-Images/5-5-01-s3-images-bucket.png" alt="Tạo S3 bucket lưu ảnh sản phẩm" style="max-width:100%;height:auto;display:block;margin:1rem auto;border:1px solid #e5e7eb;border-radius:6px;" /></p>
<p style="text-align:center;"><em>Tạo S3 bucket lưu ảnh sản phẩm</em></p>

#### 2. Upload thử ảnh sản phẩm

Upload thử ảnh sản phẩm lên Amazon S3 để kiểm tra khả năng lưu trữ media của bucket.

<p class="workshop-img"><img src="/AWS/images/5-Workshop/5.5-S3-Product-Images/5-5-02-upload-product-image.png" alt="Upload ảnh sản phẩm lên S3" style="max-width:100%;height:auto;display:block;margin:1rem auto;border:1px solid #e5e7eb;border-radius:6px;" /></p>
<p style="text-align:center;"><em>Upload ảnh sản phẩm lên S3</em></p>

#### 3. Cấu hình Bucket Policy

Cấu hình Bucket Policy cho phép public read các object trong S3 Bucket. Nhờ đó frontend có thể hiển thị ảnh sản phẩm được lưu trữ trên Amazon S3.

<p class="workshop-img"><img src="/AWS/images/5-Workshop/5.5-S3-Product-Images/5-5-03-bucket-policy.png" alt="Cấu hình bucket policy public read" style="max-width:100%;height:auto;display:block;margin:1rem auto;border:1px solid #e5e7eb;border-radius:6px;" /></p>
<p style="text-align:center;"><em>Cấu hình bucket policy public read</em></p>

Ví dụ Bucket Policy:

```json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Sid": "PublicReadGetObject",
      "Effect": "Allow",
      "Principal": "*",
      "Action": "s3:GetObject",
      "Resource": "arn:aws:s3:::clothing-store-images-dien0311/*"
    }
  ]
}
```


