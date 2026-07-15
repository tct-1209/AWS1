---
title: "Blog 3 - Lessons learned from scaling to 1 million Lambda functions"
date: 2026-07-01
weight: 3
chapter: false
pre: " <b> 3.3. </b> "
---

# AWS Architecture Blog | Lessons learned from scaling to 1 million Lambda functions

## Ná»™i dung chÃ­nh

BÃ i viáº¿t nÃ y nÃ³i vá» nhá»¯ng bÃ i há»c khi má»™t há»‡ thá»‘ng serverless phÃ¡t triá»ƒn tá»›i quy mÃ´ ráº¥t lá»›n, vá»›i hÆ¡n 1 triá»‡u **AWS Lambda functions**. Äiá»u mÃ¬nh áº¥n tÆ°á»£ng lÃ  váº¥n Ä‘á» scale khÃ´ng chá»‰ náº±m á»Ÿ viá»‡c tÄƒng tÃ i nguyÃªn, mÃ  cÃ²n náº±m á»Ÿ cÃ¡ch thiáº¿t káº¿ kiáº¿n trÃºc vÃ  quáº£n lÃ½ Ä‘á»™ phá»©c táº¡p cá»§a há»‡ thá»‘ng.

CÃ¡c thÃ nh pháº§n nhÆ° **Amazon EventBridge**, **Amazon SQS**, **AWS Lambda** vÃ  **DLQ** thÆ°á»ng Ä‘Æ°á»£c sá»­ dá»¥ng Ä‘á»ƒ xÃ¢y dá»±ng luá»“ng xá»­ lÃ½ báº¥t Ä‘á»“ng bá»™. Khi há»‡ thá»‘ng lá»›n dáº§n, viá»‡c sá»­ dá»¥ng hÃ ng Ä‘á»£i, cÆ¡ cháº¿ retry, dead-letter queue vÃ  phÃ¢n tÃ¡ch trÃ¡ch nhiá»‡m giá»¯a cÃ¡c thÃ nh pháº§n giÃºp há»‡ thá»‘ng á»•n Ä‘á»‹nh hÆ¡n.

## HÃ¬nh áº£nh bÃ i chia sáº»

<img src="/AWS/images/3-BlogsTranslated/blog-3.png" alt="Blog 3 - Lessons learned from scaling to 1 million Lambda functions" style="max-width: 100%; border: 1px solid #ddd; border-radius: 8px; margin: 16px 0;" />

## Äiá»u mÃ¬nh há»c Ä‘Æ°á»£c

- Scale á»Ÿ quy mÃ´ lá»›n cáº§n tÆ° duy kiáº¿n trÃºc, khÃ´ng chá»‰ tÄƒng tÃ i nguyÃªn.
- Event-driven architecture giÃºp cÃ¡c thÃ nh pháº§n káº¿t ná»‘i rá»i ráº¡c vÃ  dá»… má»Ÿ rá»™ng hÆ¡n.
- SQS vÃ  DLQ giÃºp há»‡ thá»‘ng xá»­ lÃ½ lá»—i tá»‘t hÆ¡n trong cÃ¡c luá»“ng báº¥t Ä‘á»“ng bá»™.
- Cáº§n chÃº Ã½ service quotas, logging, monitoring vÃ  cÃ¡ch tá»• chá»©c tÃ i nguyÃªn.
- Khi há»‡ thá»‘ng phÃ¡t triá»ƒn, viá»‡c chuáº©n hÃ³a pattern kiáº¿n trÃºc giÃºp giáº£m rá»§i ro váº­n hÃ nh.

## LiÃªn há»‡ vá»›i dá»± Ã¡n SUMMER-STORE

Dá»± Ã¡n SUMMER-STORE hiá»‡n dÃ¹ng kiáº¿n trÃºc Ä‘Æ¡n giáº£n vá»›i frontend trÃªn S3, backend trÃªn EC2 vÃ  database trÃªn RDS. Tuy nhiÃªn, cÃ¡c bÃ i há»c tá»« há»‡ thá»‘ng Lambda quy mÃ´ lá»›n váº«n ráº¥t há»¯u Ã­ch. Trong tÆ°Æ¡ng lai, nhá»¯ng tÃ¡c vá»¥ nhÆ° xá»­ lÃ½ Ä‘Æ¡n hÃ ng, gá»­i thÃ´ng bÃ¡o, xá»­ lÃ½ thanh toÃ¡n hoáº·c Ä‘á»“ng bá»™ dá»¯ liá»‡u cÃ³ thá»ƒ Ä‘Æ°á»£c tÃ¡ch thÃ nh cÃ¡c luá»“ng event-driven Ä‘á»ƒ há»‡ thá»‘ng linh hoáº¡t vÃ  dá»… má»Ÿ rá»™ng hÆ¡n.

## Link bÃ i chia sáº»

File Word hiá»‡n chÆ°a cung cáº¥p link bÃ i chia sáº» cho Blog 3.

