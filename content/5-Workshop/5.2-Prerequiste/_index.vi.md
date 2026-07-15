---
title: "Chuẩn bị triển khai"
date: 2026-07-01
weight: 2
chapter: false
pre: " <b> 5.2. </b> "
---

# Chuẩn bị triển khai

Trước khi triển khai dự án SUMMER-STORE lên AWS, cần chuẩn bị tài khoản AWS, mã nguồn frontend/backend, key pair để SSH vào EC2 và các thông tin cấu hình cho database, JWT, email, lưu trữ ảnh và VNPay.

#### Thành phần cần chuẩn bị

| Thành phần | Mục đích |
|---|---|
| AWS Account | Tạo và quản lý tài nguyên AWS |
| IAM User / Access Key | Sử dụng AWS CLI để start/stop EC2, kiểm tra tài nguyên |
| EC2 Key Pair `.pem` | SSH vào EC2 để deploy backend |
| Backend Spring Boot | Build thành file `.jar` để chạy trên EC2 |
| Frontend React/Vite | Build thành static files để upload lên S3 |
| RDS SQL Server | Database lưu user, sản phẩm, giỏ hàng, đơn hàng |
| VNPay Sandbox | Kiểm thử luồng thanh toán |

#### Các port cần dùng

| Port | Mục đích |
|---|---|
| 22 | SSH vào EC2 |
| 8080 | Backend Spring Boot public API |
| 1433 | EC2 kết nối Amazon RDS SQL Server |
| 80/443 | HTTP/HTTPS nếu mở rộng thêm domain hoặc reverse proxy |

{{% notice note %}}
Trong các file cấu hình và câu lệnh demo, không nên ghi trực tiếp mật khẩu thật. Nên dùng placeholder như `<DB_PASSWORD>`, `<JWT_SECRET>` hoặc lưu trong file `.env` trên EC2.
{{% /notice %}}


