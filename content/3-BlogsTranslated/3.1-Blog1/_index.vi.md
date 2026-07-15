---
title: "Blog 1 - Tối ưu chi phí Amazon RDS bằng cách tự động Start/Stop với AWS Lambda"
date: 2026-07-01
weight: 1
chapter: false
pre: " <b> 3.1. </b> "
---

# AWS Database Blog | Tối ưu chi phí Amazon RDS bằng cách tự động Start/Stop với AWS Lambda

## Nội dung chính

Trong quá trình tìm hiểu AWS, bài viết này giúp mình nhận ra rằng tối ưu chi phí là một phần rất quan trọng khi triển khai hệ thống lên cloud. Với **Amazon RDS**, nếu database vẫn hoạt động trong thời gian không sử dụng, hệ thống vẫn có thể phát sinh chi phí không cần thiết.

Giải pháp được đề cập là sử dụng **Amazon EventBridge Scheduler** để kích hoạt các **AWS Lambda Function** theo lịch. Một Lambda function dùng để stop RDS vào cuối ngày làm việc, function còn lại dùng để start RDS vào đầu ngày hôm sau. Các Lambda function này cần được gán **IAM Role** phù hợp để có quyền thực hiện thao tác với RDS.

## Kiến trúc tham khảo

<img src="/aws/images/3-BlogsTranslated/blog-1.png" alt="Blog 1 - Auto Start Stop Amazon RDS with AWS Lambda" style="max-width: 100%; border: 1px solid #ddd; border-radius: 8px; margin: 16px 0;" />

## Điều mình học được

- Tài nguyên cloud nên được bật/tắt theo nhu cầu sử dụng thực tế.
- EventBridge Scheduler phù hợp để tự động hóa các tác vụ chạy theo lịch.
- Lambda có thể xử lý các tác vụ vận hành nhỏ, không cần duy trì server riêng.
- IAM Role cần được phân quyền đúng để Lambda có thể start/stop RDS an toàn.
- Với môi trường học tập hoặc demo, tự động hóa việc start/stop có thể giúp tiết kiệm credit.

## Liên hệ với dự án SUMMER-STORE

Trong dự án SUMMER-STORE, mình sử dụng **Amazon RDS SQL Server** làm database chính. Khi không demo hoặc không test hệ thống, việc stop RDS và EC2 giúp giảm chi phí sử dụng AWS. Bài blog này gợi ý một hướng mở rộng tốt hơn trong tương lai: tự động hóa việc bật/tắt database thay vì thao tác thủ công trên AWS Console.

## Link bài chia sẻ

[Facebook post](https://www.facebook.com/share/p/1BZeHedGDc/)
