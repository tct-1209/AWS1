---
title: "Worklog Tuần 3"
date: 2026-07-01
weight: 3
chapter: false
pre: " <b> 1.3. </b> "
---

# Worklog Tuần 3: Amazon RDS, backup và quản lý dữ liệu quan hệ

**Thời gian thực hiện:** 04/05/2026 - 10/05/2026

## 1. Mục tiêu tuần

- Tìm hiểu Amazon RDS và các database engine phổ biến.
- Thực hành chuẩn bị VPC, DB Subnet Group và Security Group cho database.
- Nắm khái niệm backup, snapshot và khôi phục dữ liệu.

## 2. Chi tiết công việc triển khai

| Thứ | Thời gian | Nội dung công việc |
| --- | --- | --- |
| Thứ 2 | 04/05/2026 | Tìm hiểu tổng quan Amazon RDS, các engine như MySQL, PostgreSQL, SQL Server và Aurora. |
| Thứ 3 | 05/05/2026 | Chuẩn bị Security Group cho EC2 và RDS, phân biệt truy cập từ máy cá nhân và từ EC2 backend. |
| Thứ 4 | 06/05/2026 | Tạo DB Subnet Group, xem thông tin endpoint và ghi chú cách ứng dụng kết nối database. |
| Thứ 5 | 07/05/2026 | Nghiên cứu backup tự động, snapshot thủ công và nguyên tắc khôi phục khi dữ liệu gặp sự cố. |
| Thứ 6 | 08/05/2026 | Tổng hợp quy trình kết nối EC2 đến RDS và các lỗi phổ biến như timeout, sai endpoint hoặc sai inbound rule. |

## 3. Kết quả đạt được

- Hiểu cách triển khai database managed service bằng Amazon RDS.
- Biết cách cấu hình kết nối bảo mật giữa EC2 và RDS.
- Nhận thức rõ vai trò của backup/snapshot trong vận hành hệ thống.

## 4. Nguồn tài liệu tham khảo

| Nguồn | Đường dẫn | Nội dung tham khảo |
| --- | --- | --- |
| 000005 - Amazon RDS | [https://000005.awsstudygroup.com/](https://000005.awsstudygroup.com/) | RDS, DB subnet group, backup and restore |
| 000013 - AWS Backup | [https://000013.awsstudygroup.com/](https://000013.awsstudygroup.com/) | Backup strategy |
| 000043 - Database Schema Conversion & Migration | [https://000043.awsstudygroup.com/](https://000043.awsstudygroup.com/) | Database migration concepts |


