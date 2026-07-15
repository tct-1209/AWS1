---
title: "Blog 2 - Scale hệ thống không chỉ là thêm EC2"
date: 2026-07-01
weight: 2
chapter: false
pre: " <b> 3.2. </b> "
---

# AWS Compute Blog | Scale hệ thống không chỉ là thêm EC2

## Nội dung chính

Bài blog này giúp mình hiểu rằng **scale hệ thống** không chỉ đơn giản là tăng thêm số lượng EC2 Instance. Khi ứng dụng phát triển, hệ thống cần được chuẩn bị về kiến trúc, khả năng chịu lỗi, khả năng tự phục hồi và khả năng quan sát.

Một hệ thống có thể sử dụng **Auto Scaling Group** để tự động tăng/giảm số lượng instance theo tải. Tuy nhiên, để scale đáng tin cậy, ứng dụng cũng cần được triển khai trên nhiều **Availability Zone**, có cơ chế health check, giám sát tài nguyên và thiết kế ứng dụng hạn chế phụ thuộc vào trạng thái cục bộ của một server.

## Hình ảnh bài chia sẻ

<img src="/AWS/images/3-BlogsTranslated/blog-2.png" alt="Blog 2 - Scale hệ thống không chỉ là thêm EC2" style="max-width: 100%; border: 1px solid #ddd; border-radius: 8px; margin: 16px 0;" />

## Điều mình học được

- Tăng số lượng EC2 chỉ là một phần của bài toán scale.
- Auto Scaling cần đi kèm health check và chiến lược phân phối tải phù hợp.
- Multi-AZ giúp hệ thống có khả năng sẵn sàng cao hơn.
- Ứng dụng nên được thiết kế stateless để dễ mở rộng.
- Monitoring giúp phát hiện bottleneck trước khi hệ thống gặp lỗi lớn.

## Liên hệ với dự án SUMMER-STORE

Hiện tại SUMMER-STORE đang chạy backend Spring Boot trên một EC2 Instance. Đây là mô hình phù hợp cho môi trường demo. Tuy nhiên, nếu hệ thống có nhiều người dùng hơn, hướng mở rộng tiếp theo có thể là dùng **Application Load Balancer**, **Auto Scaling Group**, triển khai backend ở nhiều Availability Zone và theo dõi hệ thống bằng **Amazon CloudWatch**.

## Link bài chia sẻ

[Facebook group post](https://www.facebook.com/groups/awsstudygroupfcj/?multi_permalinks=2209334513164842&notif_id=1783618764716437&notif_t=feedback_reaction_generic&ref=notif)


