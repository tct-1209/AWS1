---
title: "Triển khai database với Amazon RDS SQL Server"
date: 2026-07-01
weight: 4
chapter: false
pre: " <b> 5.4. </b> "
---

# Triển khai database với Amazon RDS SQL Server

Khi backend được triển khai lên EC2, cấu hình database local không còn phù hợp vì `localhost` lúc này trỏ tới chính máy chủ EC2. Do đó cần sử dụng Amazon RDS để cung cấp database có thể truy cập từ backend trên AWS.

<p class="workshop-img"><img src="/aws/images/5-Workshop/5.4-Deploy-RDS-SQLServer/5-4-00-localhost-db-error.png" alt="Lỗi kết nối database local sau khi deploy EC2" style="max-width:100%;height:auto;display:block;margin:1rem auto;border:1px solid #e5e7eb;border-radius:6px;" /></p>
<p style="text-align:center;"><em>Lỗi kết nối database local sau khi deploy EC2</em></p>

#### 1. Tạo Amazon RDS SQL Server

Amazon RDS SQL Server đã được tạo thành công và chuyển sang trạng thái **Available**. Database sẵn sàng để backend Spring Boot trên EC2 kết nối.

<p class="workshop-img"><img src="/aws/images/5-Workshop/5.4-Deploy-RDS-SQLServer/5-4-01-rds-available.png" alt="Amazon RDS SQL Server Available" style="max-width:100%;height:auto;display:block;margin:1rem auto;border:1px solid #e5e7eb;border-radius:6px;" /></p>
<p style="text-align:center;"><em>Amazon RDS SQL Server Available</em></p>

#### 2. Lấy endpoint của RDS

Lấy endpoint của Amazon RDS SQL Server để cấu hình kết nối database cho backend Spring Boot trên EC2.

<p class="workshop-img"><img src="/aws/images/5-Workshop/5.4-Deploy-RDS-SQLServer/5-4-02-rds-endpoint.png" alt="Lấy endpoint RDS SQL Server" style="max-width:100%;height:auto;display:block;margin:1rem auto;border:1px solid #e5e7eb;border-radius:6px;" /></p>
<p style="text-align:center;"><em>Lấy endpoint RDS SQL Server</em></p>

#### 3. Tạo database cho dự án

Tạo database `clothing_store_backend` thành công trên Amazon RDS SQL Server. Database này được backend Spring Boot sử dụng để lưu trữ dữ liệu người dùng, sản phẩm, giỏ hàng, đơn hàng và các thông tin nghiệp vụ của hệ thống.

<p class="workshop-img"><img src="/aws/images/5-Workshop/5.4-Deploy-RDS-SQLServer/5-4-03-database-created.png" alt="Tạo database clothing_store_backend" style="max-width:100%;height:auto;display:block;margin:1rem auto;border:1px solid #e5e7eb;border-radius:6px;" /></p>
<p style="text-align:center;"><em>Tạo database clothing_store_backend</em></p>

Ví dụ lệnh kết nối RDS bằng `sqlcmd`:

```bash
sqlcmd -S "<RDS_PRIVATE_IP_OR_ENDPOINT>,1433" -U <DB_USERNAME> -C -l 120
```

Sau khi vào SQL Server prompt, tạo hoặc kiểm tra database:

```sql
SELECT name FROM sys.databases;
GO
```

#### 4. Cập nhật file `.env` để dùng RDS

Cập nhật file `.env` trên EC2 để backend Spring Boot kết nối tới Amazon RDS SQL Server thay vì database local.

<p class="workshop-img"><img src="/aws/images/5-Workshop/5.4-Deploy-RDS-SQLServer/5-4-04-env-rds.png" alt="Cập nhật .env kết nối RDS" style="max-width:100%;height:auto;display:block;margin:1rem auto;border:1px solid #e5e7eb;border-radius:6px;" /></p>
<p style="text-align:center;"><em>Cập nhật .env kết nối RDS</em></p>

{{% notice warning %}}
Không đưa mật khẩu database thật lên báo cáo hoặc source public. Nên dùng biến môi trường trong `.env` hoặc secret manager nếu triển khai production.
{{% /notice %}}
