---
title: "Các bài blogs đã dịch"
date: 2026-07-01
weight: 3
chapter: false
pre: " <b> 3. </b> "
---

# Các bài blogs đã dịch

Phần này tổng hợp 3 bài blog đã đọc, dịch/tóm tắt và chia sẻ trong quá trình tìm hiểu AWS. Nội dung tập trung vào các chủ đề gần với dự án triển khai SUMMER-STORE trên AWS: tối ưu chi phí RDS, mở rộng hệ thống với EC2 và tư duy kiến trúc khi scale Lambda ở quy mô lớn.

## Danh sách blog

### [Blog 1 - Tối ưu chi phí Amazon RDS bằng cách tự động Start/Stop với AWS Lambda](3.1-Blog1/)
Bài viết giúp hiểu cách sử dụng **Amazon EventBridge Scheduler**, **AWS Lambda** và **IAM Role** để tự động bật/tắt **Amazon RDS** theo lịch, từ đó giảm chi phí khi database không cần chạy liên tục.

### [Blog 2 - Scale hệ thống không chỉ là thêm EC2](3.2-Blog2/)
Bài viết nhấn mạnh rằng mở rộng hệ thống không đơn giản là tăng số lượng EC2, mà cần chuẩn bị kiến trúc gồm nhiều Availability Zone, Auto Scaling, health check, giám sát và thiết kế ứng dụng phù hợp.

### [Blog 3 - Lessons learned from scaling to 1 million Lambda functions](3.3-Blog3/)
Bài viết nói về bài học khi vận hành hệ thống serverless ở quy mô rất lớn, đặc biệt là tư duy event-driven, hàng đợi, DLQ, giới hạn dịch vụ, quan sát hệ thống và quản trị kiến trúc phân tán.
