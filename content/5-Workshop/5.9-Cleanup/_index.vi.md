---
title: "Dọn dẹp tài nguyên"
date: 2026-07-01
weight: 9
chapter: false
pre: " <b> 5.9. </b> "
---

# Dọn dẹp tài nguyên

Sau khi hoàn thành demo hoặc báo cáo, cần dọn dẹp hoặc tạm dừng các tài nguyên AWS để tránh phát sinh chi phí ngoài ý muốn.

#### Các tài nguyên cần kiểm tra

| Tài nguyên | Hành động khuyến nghị |
|---|---|
| Amazon EC2 | Stop instance khi không sử dụng |
| Amazon RDS | Stop database khi không demo/test |
| Elastic IP | Giữ nếu còn dùng EC2; release nếu không còn dùng |
| Amazon S3 Frontend Bucket | Giữ nếu website còn cần public |
| Amazon S3 Images Bucket | Xóa object/bucket nếu không còn dùng |
| AWS Budgets | Giữ budget để cảnh báo chi phí |

#### Lệnh start/stop EC2 bằng AWS CLI

```powershell
$INSTANCE_ID = "i-07d1af0954de7115d"
$REGION = "us-east-1"
$PROFILE = "clothing-store-v2"

aws ec2 stop-instances --instance-ids $INSTANCE_ID --region $REGION --profile $PROFILE
aws ec2 start-instances --instance-ids $INSTANCE_ID --region $REGION --profile $PROFILE
```

#### Thứ tự bật/tắt khi cần demo

Khi bắt đầu demo:

```text
Start RDS → Start EC2 → kiểm tra backend service → truy cập website
```

Khi không sử dụng:

```text
Stop EC2 → Stop RDS
```

{{% notice warning %}}
RDS có thể tự động bật lại sau một khoảng thời gian tạm dừng. Cần theo dõi Billing, Credits và Budgets thường xuyên để kiểm soát chi phí.
{{% /notice %}}
