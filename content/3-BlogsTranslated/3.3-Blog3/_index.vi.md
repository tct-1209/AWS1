---
title: "Blog 3 - Lessons learned from scaling to 1 million Lambda functions"
date: 2026-07-01
weight: 3
chapter: false
pre: " <b> 3.3. </b> "
---

# AWS Architecture Blog | Lessons learned from scaling to 1 million Lambda functions

## Nội dung chính

Bài viết này nói về những bài học khi một hệ thống serverless phát triển tới quy mô rất lớn, với hơn 1 triệu **AWS Lambda functions**. Điều mình ấn tượng là vấn đề scale không chỉ nằm ở việc tăng tài nguyên, mà còn nằm ở cách thiết kế kiến trúc và quản lý độ phức tạp của hệ thống.

Các thành phần như **Amazon EventBridge**, **Amazon SQS**, **AWS Lambda** và **DLQ** thường được sử dụng để xây dựng luồng xử lý bất đồng bộ. Khi hệ thống lớn dần, việc sử dụng hàng đợi, cơ chế retry, dead-letter queue và phân tách trách nhiệm giữa các thành phần giúp hệ thống ổn định hơn.

## Hình ảnh bài chia sẻ

<img src="/AWS/images/3-BlogsTranslated/blog-3.png" alt="Blog 3 - Lessons learned from scaling to 1 million Lambda functions" style="max-width: 100%; border: 1px solid #ddd; border-radius: 8px; margin: 16px 0;" />

## Điều mình học được

- Scale ở quy mô lớn cần tư duy kiến trúc, không chỉ tăng tài nguyên.
- Event-driven architecture giúp các thành phần kết nối rời rạc và dễ mở rộng hơn.
- SQS và DLQ giúp hệ thống xử lý lỗi tốt hơn trong các luồng bất đồng bộ.
- Cần chú ý service quotas, logging, monitoring và cách tổ chức tài nguyên.
- Khi hệ thống phát triển, việc chuẩn hóa pattern kiến trúc giúp giảm rủi ro vận hành.

## Liên hệ với dự án SUMMER-STORE

Dự án SUMMER-STORE hiện dùng kiến trúc đơn giản với frontend trên S3, backend trên EC2 và database trên RDS. Tuy nhiên, các bài học từ hệ thống Lambda quy mô lớn vẫn rất hữu ích. Trong tương lai, những tác vụ như xử lý đơn hàng, gửi thông báo, xử lý thanh toán hoặc đồng bộ dữ liệu có thể được tách thành các luồng event-driven để hệ thống linh hoạt và dễ mở rộng hơn.

## Link bài chia sẻ

File Word hiện chưa cung cấp link bài chia sẻ cho Blog 3.


