---
title: "Workshop triển khai SUMMER-STORE trên AWS"
date: 2026-07-01
weight: 5
chapter: false
pre: " <b> 5. </b> "
---


# Triển khai website thương mại điện tử SUMMER-STORE trên AWS

#### Tổng quan

Workshop này trình bày quá trình triển khai dự án **SUMMER-STORE** từ môi trường local lên AWS. Hệ thống gồm frontend React/Vite, backend Spring Boot và database SQL Server. Các dịch vụ AWS được sử dụng gồm **Amazon S3**, **Amazon EC2**, **Amazon RDS SQL Server**, **Elastic IP**, **IAM**, **AWS CLI**, **Amazon CloudWatch** và **AWS Budgets**.

#### Kiến trúc triển khai

Người dùng truy cập website qua frontend được host trên **Amazon S3 Static Website Hosting**. Sau khi tải frontend về trình duyệt, ứng dụng React/Vite gọi API đến backend thông qua **Elastic IP** gắn với **Amazon EC2**. Backend Spring Boot xử lý nghiệp vụ và kết nối **Amazon RDS SQL Server** để đọc/ghi dữ liệu. Với chức năng thanh toán, backend tạo URL thanh toán **VNPay Sandbox** và nhận callback/redirect để cập nhật trạng thái đơn hàng.

<p class="workshop-img"><img src="/aws/images/5-Workshop/5.1-Workshop-overview/5-1-01-workflow-aws.png" alt="Workflow triển khai SUMMER-STORE trên AWS" style="max-width:100%;height:auto;display:block;margin:1rem auto;border:1px solid #e5e7eb;border-radius:6px;" /></p>
<p style="text-align:center;"><em>Workflow triển khai SUMMER-STORE trên AWS</em></p>

#### Nội dung

1. [Tổng quan workshop](5.1-Workshop-overview/)
2. [Chuẩn bị triển khai](5.2-Prerequiste/)
3. [Triển khai Backend Spring Boot trên Amazon EC2](5.3-Deploy-EC2-Backend/)
4. [Triển khai database với Amazon RDS SQL Server](5.4-Deploy-RDS-SQLServer/)
5. [Lưu trữ ảnh sản phẩm bằng Amazon S3](5.5-S3-Product-Images/)
6. [Deploy frontend React với Amazon S3 Static Website Hosting](5.6-Deploy-S3-Frontend/)
7. [Kiểm thử backend, Elastic IP và API](5.7-ElasticIP-Systemd-Test/)
8. [Kiểm thử workflow tổng thể và thanh toán VNPay](5.8-Workflow-Final-Test/)
9. [Dọn dẹp tài nguyên](5.9-Cleanup/)
