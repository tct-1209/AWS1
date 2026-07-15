---
title: "Dá»n dáº¹p tÃ i nguyÃªn"
date: 2026-07-01
weight: 9
chapter: false
pre: " <b> 5.9. </b> "
---

# Dá»n dáº¹p tÃ i nguyÃªn

Sau khi hoÃ n thÃ nh demo hoáº·c bÃ¡o cÃ¡o, cáº§n dá»n dáº¹p hoáº·c táº¡m dá»«ng cÃ¡c tÃ i nguyÃªn AWS Ä‘á»ƒ trÃ¡nh phÃ¡t sinh chi phÃ­ ngoÃ i Ã½ muá»‘n.

#### CÃ¡c tÃ i nguyÃªn cáº§n kiá»ƒm tra

| TÃ i nguyÃªn | HÃ nh Ä‘á»™ng khuyáº¿n nghá»‹ |
|---|---|
| Amazon EC2 | Stop instance khi khÃ´ng sá»­ dá»¥ng |
| Amazon RDS | Stop database khi khÃ´ng demo/test |
| Elastic IP | Giá»¯ náº¿u cÃ²n dÃ¹ng EC2; release náº¿u khÃ´ng cÃ²n dÃ¹ng |
| Amazon S3 Frontend Bucket | Giá»¯ náº¿u website cÃ²n cáº§n public |
| Amazon S3 Images Bucket | XÃ³a object/bucket náº¿u khÃ´ng cÃ²n dÃ¹ng |
| AWS Budgets | Giá»¯ budget Ä‘á»ƒ cáº£nh bÃ¡o chi phÃ­ |

#### Lá»‡nh start/stop EC2 báº±ng AWS CLI

```powershell
$INSTANCE_ID = "i-07d1af0954de7115d"
$REGION = "us-east-1"
$PROFILE = "clothing-store-v2"

aws ec2 stop-instances --instance-ids $INSTANCE_ID --region $REGION --profile $PROFILE
aws ec2 start-instances --instance-ids $INSTANCE_ID --region $REGION --profile $PROFILE
```

#### Thá»© tá»± báº­t/táº¯t khi cáº§n demo

Khi báº¯t Ä‘áº§u demo:

```text
Start RDS â†’ Start EC2 â†’ kiá»ƒm tra backend service â†’ truy cáº­p website
```

Khi khÃ´ng sá»­ dá»¥ng:

```text
Stop EC2 â†’ Stop RDS
```

{{% notice warning %}}
RDS cÃ³ thá»ƒ tá»± Ä‘á»™ng báº­t láº¡i sau má»™t khoáº£ng thá»i gian táº¡m dá»«ng. Cáº§n theo dÃµi Billing, Credits vÃ  Budgets thÆ°á»ng xuyÃªn Ä‘á»ƒ kiá»ƒm soÃ¡t chi phÃ­.
{{% /notice %}}

