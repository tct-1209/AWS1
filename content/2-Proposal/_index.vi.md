---
title: "Bản đề xuất"
date: 2026-07-01
weight: 2
chapter: false
pre: " <b> 2. </b> "
---

# Bản đề xuất triển khai dự án SUMMER-STORE trên AWS

## 1. Tên đề tài

**Triển khai website thương mại điện tử SUMMER-STORE trên nền tảng AWS**

Dự án tập trung vào việc đưa hệ thống website bán quần áo **SUMMER-STORE** từ môi trường local lên AWS. Hệ thống bao gồm frontend React/Vite, backend Spring Boot, database SQL Server và chức năng thanh toán thử nghiệm qua VNPay Sandbox.

## 2. Lý do chọn đề tài

Trong thực tế, một website thương mại điện tử không chỉ cần chạy được trên máy local mà còn cần có khả năng truy cập qua Internet, lưu trữ dữ liệu tập trung, xử lý API ổn định và dễ theo dõi chi phí vận hành. Vì vậy, đề tài này được lựa chọn nhằm thực hành quy trình triển khai một hệ thống fullstack lên cloud thông qua các dịch vụ AWS cơ bản.

Việc triển khai SUMMER-STORE trên AWS giúp sinh viên hiểu rõ hơn cách kết hợp **Amazon S3**, **Amazon EC2**, **Amazon RDS**, **Elastic IP**, **IAM**, **AWS CLI**, **CloudWatch** và **AWS Budgets** trong một bài toán gần với thực tế.

## 3. Mục tiêu đề tài

- Triển khai frontend React/Vite bằng **Amazon S3 Static Website Hosting**.
- Triển khai backend Spring Boot trên **Amazon EC2**.
- Sử dụng **Amazon RDS for SQL Server** để lưu dữ liệu hệ thống.
- Cấu hình **Elastic IP** để cố định địa chỉ truy cập API backend.
- Cấu hình **Security Group** cho SSH, API backend và kết nối database.
- Lưu trữ ảnh sản phẩm bằng **Amazon S3**.
- Kiểm thử các chức năng chính: đăng nhập, quản lý sản phẩm, tồn kho, đơn hàng và thanh toán VNPay Sandbox.
- Theo dõi hoạt động và chi phí bằng **CloudWatch**, **AWS Budgets** và **Billing**.

## 4. Phạm vi thực hiện

Phạm vi đề tài tập trung vào triển khai hệ thống ở mức demo/thực tập. Các chức năng chính gồm đăng ký, đăng nhập, hiển thị sản phẩm, quản lý sản phẩm, quản lý biến thể, quản lý tồn kho, quản lý đơn hàng và thanh toán thử nghiệm bằng VNPay Sandbox.

Đề tài chưa triển khai các thành phần nâng cao như Load Balancer, Auto Scaling, Route 53, CloudFront CDN hoặc CI/CD tự động hoàn chỉnh. Những thành phần này có thể được bổ sung trong giai đoạn mở rộng sau.

## 5. Kiến trúc đề xuất

Người dùng hoặc admin truy cập website thông qua trình duyệt. Frontend được host trên **Amazon S3 Static Website Hosting**. Sau khi tải giao diện về trình duyệt, ứng dụng React/Vite gọi API tới backend thông qua **Elastic IP** của EC2. Backend Spring Boot chạy trên **Amazon EC2**, xử lý nghiệp vụ và kết nối tới **Amazon RDS SQL Server** để đọc/ghi dữ liệu. Với chức năng thanh toán, backend tạo URL thanh toán VNPay Sandbox và nhận redirect/callback để cập nhật trạng thái đơn hàng.

<p class="workshop-img"><img src="/aws/images/2-Proposal/summer-store-workflow.png" alt="Workflow triển khai SUMMER-STORE trên AWS" style="max-width:100%;height:auto;display:block;margin:1rem auto;border:1px solid #e5e7eb;border-radius:6px;" /></p>
<p style="text-align:center;"><em>Workflow triển khai SUMMER-STORE trên AWS</em></p>

## 6. Các dịch vụ AWS sử dụng

| Dịch vụ | Vai trò trong dự án |
|---|---|
| **Amazon S3 Static Website Hosting** | Host frontend React/Vite gồm `index.html`, JavaScript, CSS và tài nguyên tĩnh. |
| **Amazon S3 Product Images Bucket** | Lưu trữ ảnh sản phẩm và media của hệ thống. |
| **Amazon EC2** | Chạy backend Spring Boot bằng file `app.jar`. |
| **Elastic IP** | Cố định địa chỉ backend API, ví dụ `13.223.11.215:8080`. |
| **Amazon RDS for SQL Server** | Lưu trữ dữ liệu người dùng, sản phẩm, giỏ hàng, đơn hàng và biến thể sản phẩm. |
| **Security Group** | Kiểm soát truy cập port `22`, `8080`, `80/443` và `1433`. |
| **AWS IAM** | Quản lý user, quyền truy cập và access key cho AWS CLI. |
| **AWS CLI** | Hỗ trợ start/stop EC2, kiểm tra trạng thái tài nguyên và thao tác với AWS từ máy local. |
| **Amazon CloudWatch** | Theo dõi log và trạng thái vận hành cơ bản. |
| **AWS Budgets / Billing** | Theo dõi credit và chi phí sử dụng AWS. |

## 7. Thiết kế thành phần

### 7.1 Frontend

Frontend được phát triển bằng React/Vite. Sau khi build, các file static trong thư mục `dist` được upload lên S3 bucket frontend để người dùng có thể truy cập website qua S3 website endpoint.

<p class="workshop-img"><img src="/aws/images/2-Proposal/s3-frontend-success.png" alt="Frontend triển khai trên Amazon S3" style="max-width:100%;height:auto;display:block;margin:1rem auto;border:1px solid #e5e7eb;border-radius:6px;" /></p>
<p style="text-align:center;"><em>Frontend SUMMER-STORE sau khi triển khai lên Amazon S3</em></p>

### 7.2 Backend

Backend được phát triển bằng Spring Boot. Ứng dụng được build thành file `.jar`, upload lên EC2 và chạy bằng Java 17. Backend tiếp nhận request từ frontend, xử lý nghiệp vụ và trả dữ liệu API cho website.

<p class="workshop-img"><img src="/aws/images/2-Proposal/ec2-backend-instance.png" alt="Amazon EC2 chạy backend Spring Boot" style="max-width:100%;height:auto;display:block;margin:1rem auto;border:1px solid #e5e7eb;border-radius:6px;" /></p>
<p style="text-align:center;"><em>Amazon EC2 được sử dụng để triển khai backend Spring Boot</em></p>

### 7.3 Database

Database sử dụng Amazon RDS for SQL Server. Backend kết nối đến RDS thông qua JDBC để lưu trữ và truy vấn dữ liệu như tài khoản người dùng, sản phẩm, biến thể sản phẩm, giỏ hàng và đơn hàng.

<p class="workshop-img"><img src="/aws/images/2-Proposal/rds-sqlserver-available.png" alt="Amazon RDS SQL Server" style="max-width:100%;height:auto;display:block;margin:1rem auto;border:1px solid #e5e7eb;border-radius:6px;" /></p>
<p style="text-align:center;"><em>Amazon RDS SQL Server ở trạng thái Available</em></p>

### 7.4 Thanh toán

VNPay Sandbox là dịch vụ thanh toán bên ngoài AWS. Backend tạo payment URL, chuyển người dùng sang trang thanh toán VNPay và nhận kết quả redirect/callback để cập nhật trạng thái đơn hàng trong database.

## 8. Kế hoạch triển khai

| Giai đoạn | Nội dung thực hiện |
|---|---|
| Giai đoạn 1 | Chuẩn bị mã nguồn frontend, backend, tài khoản AWS, IAM user và AWS CLI. |
| Giai đoạn 2 | Tạo EC2, cấu hình Security Group, cài Java 17 và deploy backend Spring Boot. |
| Giai đoạn 3 | Tạo Amazon RDS SQL Server, tạo database `clothing_store_backend` và cập nhật file `.env`. |
| Giai đoạn 4 | Tạo S3 bucket lưu ảnh sản phẩm và cấu hình bucket policy phù hợp. |
| Giai đoạn 5 | Build frontend React/Vite, upload file static lên S3 và bật Static Website Hosting. |
| Giai đoạn 6 | Gắn Elastic IP, kiểm thử API, đăng nhập, quản lý sản phẩm, đơn hàng và VNPay Sandbox. |
| Giai đoạn 7 | Theo dõi vận hành, kiểm tra chi phí và dọn dẹp tài nguyên không cần thiết. |

## 9. Kết quả mong đợi

Sau khi hoàn thành, hệ thống SUMMER-STORE có thể hoạt động trên môi trường AWS với các kết quả sau:

- Người dùng truy cập được frontend thông qua S3 website endpoint.
- Frontend gọi được API backend thông qua Elastic IP.
- Backend Spring Boot chạy ổn định trên EC2 bằng `systemd service`.
- Dữ liệu được lưu trữ và truy vấn từ Amazon RDS SQL Server.
- Admin có thể quản lý sản phẩm, tồn kho và đơn hàng.
- Người dùng có thể đặt hàng và thanh toán thử nghiệm qua VNPay Sandbox.
- Người thực hiện nắm được quy trình triển khai website fullstack lên AWS và cách theo dõi chi phí cloud.

## 10. Rủi ro và hướng xử lý

| Rủi ro | Hướng xử lý |
|---|---|
| Backend không truy cập được từ frontend | Kiểm tra Security Group, port `8080`, Elastic IP và CORS. |
| EC2 không kết nối được RDS | Kiểm tra endpoint RDS, port `1433`, Security Group và thông tin `.env`. |
| Ảnh sản phẩm không hiển thị | Kiểm tra S3 bucket policy, object URL và quyền public read nếu cần. |
| VNPay Sandbox lỗi callback | Kiểm tra `returnUrl`, mã cấu hình VNPay và chữ ký bảo mật. |
| Chi phí AWS vượt dự kiến | Theo dõi Billing/Budgets, stop EC2/RDS khi không sử dụng. |

## 11. Hướng mở rộng

Trong tương lai, hệ thống có thể được mở rộng bằng cách sử dụng **CloudFront** để tăng tốc frontend, **Route 53** để gắn tên miền riêng, **Application Load Balancer** và **Auto Scaling** để tăng độ sẵn sàng cho backend, cũng như triển khai CI/CD để tự động build và deploy mã nguồn.
