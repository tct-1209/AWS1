---
title: "Kiểm thử workflow tổng thể và thanh toán VNPay"
date: 2026-07-01
weight: 8
chapter: false
pre: " <b> 5.8. </b> "
---

# Kiểm thử workflow tổng thể và thanh toán VNPay

Sau khi hoàn tất triển khai frontend, backend và database, tiến hành kiểm thử workflow tổng thể của hệ thống SUMMER-STORE.

<p class="workshop-img"><img src="/aws/images/5-Workshop/5.1-Workshop-overview/5-1-01-workflow-aws.png" alt="Workflow tổng thể SUMMER-STORE trên AWS" style="max-width:100%;height:auto;display:block;margin:1rem auto;border:1px solid #e5e7eb;border-radius:6px;" /></p>
<p style="text-align:center;"><em>Workflow tổng thể SUMMER-STORE trên AWS</em></p>

#### Luồng kiểm thử chính

1. Truy cập website SUMMER-STORE qua S3 website endpoint.
2. Đăng nhập tài khoản user hoặc admin.
3. Frontend gọi API backend thông qua Elastic IP `13.223.11.215:8080`.
4. Backend EC2 xử lý nghiệp vụ và đọc/ghi dữ liệu vào Amazon RDS SQL Server.
5. Người dùng tạo đơn hàng và chọn thanh toán VNPay Sandbox.
6. Backend tạo URL thanh toán và redirect người dùng sang VNPay.
7. Sau khi thanh toán, VNPay redirect/callback về backend.
8. Backend cập nhật trạng thái đơn hàng trong database.

#### Kết quả đạt được

- Website frontend truy cập được từ Internet thông qua Amazon S3.
- Backend Spring Boot chạy ổn định trên Amazon EC2.
- API backend hoạt động qua Elastic IP và port 8080.
- Amazon RDS SQL Server lưu trữ được dữ liệu hệ thống.
- Ảnh sản phẩm được lưu trữ và hiển thị từ Amazon S3.
- Chức năng đăng nhập, quản lý sản phẩm, tồn kho, đơn hàng và thanh toán VNPay Sandbox được kiểm thử ở mức demo.
