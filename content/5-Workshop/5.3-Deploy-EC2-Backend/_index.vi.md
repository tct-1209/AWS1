---
title: "Triển khai Backend Spring Boot trên Amazon EC2"
date: 2026-07-01
weight: 3
chapter: false
pre: " <b> 5.3. </b> "
---

# Triển khai Backend Spring Boot trên Amazon EC2

Ở bước này, backend Spring Boot của dự án được triển khai lên Amazon EC2. EC2 đóng vai trò là server chạy ứng dụng backend, tiếp nhận request từ frontend và kết nối tới database RDS.

#### 1. Khởi tạo EC2 Instance

Khởi tạo EC2 Instance để triển khai backend Spring Boot của dự án.

<p class="workshop-img"><img src="/aws/images/5-Workshop/5.3-Deploy-EC2-Backend/5-3-01-ec2-instance.png" alt="Khởi tạo EC2 Instance" style="max-width:100%;height:auto;display:block;margin:1rem auto;border:1px solid #e5e7eb;border-radius:6px;" /></p>
<p style="text-align:center;"><em>Khởi tạo EC2 Instance</em></p>

#### 2. Cấu hình Security Group cho EC2

Cấu hình Security Group cho EC2. Port `22` dùng để SSH, port `8080` dùng để chạy backend Spring Boot, port `80/443` dùng cho HTTP và HTTPS nếu cần mở rộng.

<p class="workshop-img"><img src="/aws/images/5-Workshop/5.3-Deploy-EC2-Backend/5-3-02-security-group-ec2.png" alt="Cấu hình Security Group cho EC2" style="max-width:100%;height:auto;display:block;margin:1rem auto;border:1px solid #e5e7eb;border-radius:6px;" /></p>
<p style="text-align:center;"><em>Cấu hình Security Group cho EC2</em></p>

#### 3. Kết nối EC2 bằng SSH

Kết nối thành công vào EC2 thông qua SSH để cài đặt môi trường và triển khai backend.

<p class="workshop-img"><img src="/aws/images/5-Workshop/5.3-Deploy-EC2-Backend/5-3-03-ssh-connection.png" alt="Kết nối SSH vào EC2" style="max-width:100%;height:auto;display:block;margin:1rem auto;border:1px solid #e5e7eb;border-radius:6px;" /></p>
<p style="text-align:center;"><em>Kết nối SSH vào EC2</em></p>

Ví dụ lệnh SSH:

```bash
ssh -i "backend.pem" ubuntu@13.223.11.215
```

#### 4. Cài đặt Java 17

Cài đặt Java 17 trên EC2 để chạy ứng dụng Spring Boot.

<p class="workshop-img"><img src="/aws/images/5-Workshop/5.3-Deploy-EC2-Backend/5-3-04-java17.png" alt="Kiểm tra Java 17 trên EC2" style="max-width:100%;height:auto;display:block;margin:1rem auto;border:1px solid #e5e7eb;border-radius:6px;" /></p>
<p style="text-align:center;"><em>Kiểm tra Java 17 trên EC2</em></p>

#### 5. Build backend bằng Maven

Build backend Spring Boot thành công bằng Maven. File `.jar` được tạo trong thư mục `target` để chuẩn bị triển khai lên Amazon EC2.

<p class="workshop-img"><img src="/aws/images/5-Workshop/5.3-Deploy-EC2-Backend/5-3-05-maven-build.png" alt="Build backend bằng Maven" style="max-width:100%;height:auto;display:block;margin:1rem auto;border:1px solid #e5e7eb;border-radius:6px;" /></p>
<p style="text-align:center;"><em>Build backend bằng Maven</em></p>

Ví dụ lệnh build:

```bash
./mvnw clean package -DskipTests
```

#### 6. Kiểm tra file `.jar` sau khi build

File `.jar` được tạo sau quá trình build, đây là artifact dùng để deploy backend lên EC2.

<p class="workshop-img"><img src="/aws/images/5-Workshop/5.3-Deploy-EC2-Backend/5-3-06-target-jar.png" alt="File JAR trong thư mục target" style="max-width:100%;height:auto;display:block;margin:1rem auto;border:1px solid #e5e7eb;border-radius:6px;" /></p>
<p style="text-align:center;"><em>File JAR trong thư mục target</em></p>

#### 7. Upload file `.jar` lên EC2

Upload file backend Spring Boot `.jar` từ máy local lên EC2 thành công bằng SCP. File được đổi tên thành `app.jar` để dễ quản lý khi chạy ứng dụng trên server.

<p class="workshop-img"><img src="/aws/images/5-Workshop/5.3-Deploy-EC2-Backend/5-3-07-upload-app-jar.png" alt="Upload app.jar lên EC2" style="max-width:100%;height:auto;display:block;margin:1rem auto;border:1px solid #e5e7eb;border-radius:6px;" /></p>
<p style="text-align:center;"><em>Upload app.jar lên EC2</em></p>

Ví dụ lệnh upload:

```bash
scp -i "backend.pem" target/clothing-store-backend-0.0.1-SNAPSHOT.jar ubuntu@13.223.11.215:/home/ubuntu/clothing-store/app.jar
```

#### 8. Tạo file `.env` trên EC2

Tạo file `.env` trên EC2 để lưu các biến môi trường cần thiết cho backend như cấu hình RDS, JWT, email, lưu trữ ảnh và VNPay. File `.env` được đặt cùng thư mục với `app.jar` để Spring Boot có thể đọc cấu hình khi khởi động.

<p class="workshop-img"><img src="/aws/images/5-Workshop/5.3-Deploy-EC2-Backend/5-3-08-env-file.png" alt="Tạo file .env trên EC2" style="max-width:100%;height:auto;display:block;margin:1rem auto;border:1px solid #e5e7eb;border-radius:6px;" /></p>
<p style="text-align:center;"><em>Tạo file .env trên EC2</em></p>
