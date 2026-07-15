---
title: "Blog 1 - Tá»‘i Æ°u chi phÃ­ Amazon RDS báº±ng cÃ¡ch tá»± Ä‘á»™ng Start/Stop vá»›i AWS Lambda"
date: 2026-07-01
weight: 1
chapter: false
pre: " <b> 3.1. </b> "
---

# AWS Database Blog | Tá»‘i Æ°u chi phÃ­ Amazon RDS báº±ng cÃ¡ch tá»± Ä‘á»™ng Start/Stop vá»›i AWS Lambda

## Ná»™i dung chÃ­nh

Trong quÃ¡ trÃ¬nh tÃ¬m hiá»ƒu AWS, bÃ i viáº¿t nÃ y giÃºp mÃ¬nh nháº­n ra ráº±ng tá»‘i Æ°u chi phÃ­ lÃ  má»™t pháº§n ráº¥t quan trá»ng khi triá»ƒn khai há»‡ thá»‘ng lÃªn cloud. Vá»›i **Amazon RDS**, náº¿u database váº«n hoáº¡t Ä‘á»™ng trong thá»i gian khÃ´ng sá»­ dá»¥ng, há»‡ thá»‘ng váº«n cÃ³ thá»ƒ phÃ¡t sinh chi phÃ­ khÃ´ng cáº§n thiáº¿t.

Giáº£i phÃ¡p Ä‘Æ°á»£c Ä‘á» cáº­p lÃ  sá»­ dá»¥ng **Amazon EventBridge Scheduler** Ä‘á»ƒ kÃ­ch hoáº¡t cÃ¡c **AWS Lambda Function** theo lá»‹ch. Má»™t Lambda function dÃ¹ng Ä‘á»ƒ stop RDS vÃ o cuá»‘i ngÃ y lÃ m viá»‡c, function cÃ²n láº¡i dÃ¹ng Ä‘á»ƒ start RDS vÃ o Ä‘áº§u ngÃ y hÃ´m sau. CÃ¡c Lambda function nÃ y cáº§n Ä‘Æ°á»£c gÃ¡n **IAM Role** phÃ¹ há»£p Ä‘á»ƒ cÃ³ quyá»n thá»±c hiá»‡n thao tÃ¡c vá»›i RDS.

## Kiáº¿n trÃºc tham kháº£o

<img src="/AWS/images/3-BlogsTranslated/blog-1.png" alt="Blog 1 - Auto Start Stop Amazon RDS with AWS Lambda" style="max-width: 100%; border: 1px solid #ddd; border-radius: 8px; margin: 16px 0;" />

## Äiá»u mÃ¬nh há»c Ä‘Æ°á»£c

- TÃ i nguyÃªn cloud nÃªn Ä‘Æ°á»£c báº­t/táº¯t theo nhu cáº§u sá»­ dá»¥ng thá»±c táº¿.
- EventBridge Scheduler phÃ¹ há»£p Ä‘á»ƒ tá»± Ä‘á»™ng hÃ³a cÃ¡c tÃ¡c vá»¥ cháº¡y theo lá»‹ch.
- Lambda cÃ³ thá»ƒ xá»­ lÃ½ cÃ¡c tÃ¡c vá»¥ váº­n hÃ nh nhá», khÃ´ng cáº§n duy trÃ¬ server riÃªng.
- IAM Role cáº§n Ä‘Æ°á»£c phÃ¢n quyá»n Ä‘Ãºng Ä‘á»ƒ Lambda cÃ³ thá»ƒ start/stop RDS an toÃ n.
- Vá»›i mÃ´i trÆ°á»ng há»c táº­p hoáº·c demo, tá»± Ä‘á»™ng hÃ³a viá»‡c start/stop cÃ³ thá»ƒ giÃºp tiáº¿t kiá»‡m credit.

## LiÃªn há»‡ vá»›i dá»± Ã¡n SUMMER-STORE

Trong dá»± Ã¡n SUMMER-STORE, mÃ¬nh sá»­ dá»¥ng **Amazon RDS SQL Server** lÃ m database chÃ­nh. Khi khÃ´ng demo hoáº·c khÃ´ng test há»‡ thá»‘ng, viá»‡c stop RDS vÃ  EC2 giÃºp giáº£m chi phÃ­ sá»­ dá»¥ng AWS. BÃ i blog nÃ y gá»£i Ã½ má»™t hÆ°á»›ng má»Ÿ rá»™ng tá»‘t hÆ¡n trong tÆ°Æ¡ng lai: tá»± Ä‘á»™ng hÃ³a viá»‡c báº­t/táº¯t database thay vÃ¬ thao tÃ¡c thá»§ cÃ´ng trÃªn AWS Console.

## Link bÃ i chia sáº»

[Facebook post](https://www.facebook.com/share/p/1BZeHedGDc/)

