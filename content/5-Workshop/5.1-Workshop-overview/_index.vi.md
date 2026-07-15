---
title: "Tổng quan workshop"
date: 2026-07-01
weight: 1
chapter: false
pre: " <b> 5.1. </b> "
---

# Tổng quan workshop

Phần workshop tập trung vào việc triển khai website thương mại điện tử **SUMMER-STORE** lên AWS. Dự án ban đầu chạy local, sau đó được đưa lên cloud để người dùng có thể truy cập frontend qua Internet, backend hoạt động ổn định trên EC2 và dữ liệu được lưu trên Amazon RDS SQL Server.

#### Mục tiêu

- Triển khai backend Spring Boot lên **Amazon EC2**.
- Sử dụng **Amazon RDS SQL Server** làm database chính cho hệ thống.
- Host frontend React/Vite bằng **Amazon S3 Static Website Hosting**.
- Cố định địa chỉ backend bằng **Elastic IP**.
- Cấu hình Security Group cho SSH, API backend và database.
- Kiểm thử đăng nhập, quản lý sản phẩm, tồn kho, đơn hàng và thanh toán VNPay Sandbox.
- Theo dõi vận hành và chi phí bằng CloudWatch, Budgets và Billing.

#### Workflow tổng thể

<p class="workshop-img"><img src="/aws/images/5-Workshop/5.1-Workshop-overview/5-1-01-workflow-aws.png" alt="Workflow triển khai SUMMER-STORE trên AWS" style="max-width:100%;height:auto;display:block;margin:1rem auto;border:1px solid #e5e7eb;border-radius:6px;" /></p>
<p style="text-align:center;"><em>Workflow triển khai SUMMER-STORE trên AWS</em></p>

#### Luồng hoạt động chính

1. **User/Admin truy cập website** thông qua trình duyệt.
2. **Amazon S3 trả frontend** gồm `index.html`, JavaScript, CSS và hình ảnh.
3. **Frontend gọi API backend** thông qua Elastic IP `13.223.11.215:8080`.
4. **Amazon EC2 xử lý nghiệp vụ** và kết nối Amazon RDS SQL Server để đọc/ghi dữ liệu.
5. **VNPay Sandbox xử lý thanh toán**, sau đó redirect/callback về backend để cập nhật trạng thái đơn hàng.
