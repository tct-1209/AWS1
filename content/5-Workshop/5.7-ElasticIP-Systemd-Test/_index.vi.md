---
title: "Kiểm thử backend, Elastic IP và API"
date: 2026-07-01
weight: 7
chapter: false
pre: " <b> 5.7. </b> "
---

# Kiểm thử backend, Elastic IP và API

Sau khi triển khai backend lên EC2 và cấu hình frontend gọi API qua Elastic IP, cần kiểm tra port 8080, endpoint API và trạng thái chạy của ứng dụng backend.

#### 1. Kiểm tra port 8080 từ máy local

Kiểm tra kết nối từ máy local tới backend EC2 qua port `8080`. Kết quả `TcpTestSucceeded: True` xác nhận Security Group và network đã cho phép truy cập API từ bên ngoài.

<p class="workshop-img"><img src="/AWS/images/5-Workshop/5.7-ElasticIP-Systemd-Test/5-7-01-test-port-8080.png" alt="Test port 8080 từ máy local" style="max-width:100%;height:auto;display:block;margin:1rem auto;border:1px solid #e5e7eb;border-radius:6px;" /></p>
<p style="text-align:center;"><em>Test port 8080 từ máy local</em></p>

Ví dụ lệnh PowerShell:

```powershell
Test-NetConnection 13.223.11.215 -Port 8080
```

#### 2. Kiểm tra endpoint `/v3/api-docs`

Endpoint `/v3/api-docs` trả về tài liệu OpenAPI JSON, xác nhận backend Spring Boot đã public API thành công trên EC2 thông qua port 8080.

<p class="workshop-img"><img src="/AWS/images/5-Workshop/5.7-ElasticIP-Systemd-Test/5-7-02-api-docs-browser.png" alt="Kiểm tra api-docs trên trình duyệt" style="max-width:100%;height:auto;display:block;margin:1rem auto;border:1px solid #e5e7eb;border-radius:6px;" /></p>
<p style="text-align:center;"><em>Kiểm tra api-docs trên trình duyệt</em></p>

#### 3. Kiểm tra trực tiếp trên EC2

Kiểm tra trực tiếp trên EC2 cho thấy backend đang chạy ổn định ở port `8080` và endpoint `/v3/api-docs` trả về HTTP 200.

<p class="workshop-img"><img src="/AWS/images/5-Workshop/5.7-ElasticIP-Systemd-Test/5-7-03-curl-api-docs.png" alt="curl localhost api-docs trên EC2" style="max-width:100%;height:auto;display:block;margin:1rem auto;border:1px solid #e5e7eb;border-radius:6px;" /></p>
<p style="text-align:center;"><em>curl localhost api-docs trên EC2</em></p>

Ví dụ lệnh kiểm tra:

```bash
curl -I http://localhost:8080/v3/api-docs
```

#### 4. Kiểm tra file triển khai trên EC2

File `app.jar` là backend Spring Boot đã được build và upload lên EC2. File `.env` lưu các biến môi trường như cấu hình RDS, JWT, email, lưu trữ ảnh và VNPay.

<p class="workshop-img"><img src="/AWS/images/5-Workshop/5.7-ElasticIP-Systemd-Test/5-7-04-app-env-final.png" alt="Kiểm tra app.jar và .env trên EC2" style="max-width:100%;height:auto;display:block;margin:1rem auto;border:1px solid #e5e7eb;border-radius:6px;" /></p>
<p style="text-align:center;"><em>Kiểm tra app.jar và .env trên EC2</em></p>

#### 5. Chạy backend bằng systemd service

Để backend luôn chạy sau khi đóng SSH/PowerShell, tạo service `clothing-store-backend` bằng systemd.

Một số lệnh kiểm tra service:

```bash
sudo systemctl restart clothing-store-backend
sudo systemctl status clothing-store-backend --no-pager
```

Khi service hiển thị `active (running)`, backend có thể tiếp tục hoạt động kể cả khi đóng terminal SSH.


