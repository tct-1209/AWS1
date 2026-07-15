---
title: "Blog 2 - Scale há»‡ thá»‘ng khÃ´ng chá»‰ lÃ  thÃªm EC2"
date: 2026-07-01
weight: 2
chapter: false
pre: " <b> 3.2. </b> "
---

# AWS Compute Blog | Scale há»‡ thá»‘ng khÃ´ng chá»‰ lÃ  thÃªm EC2

## Ná»™i dung chÃ­nh

BÃ i blog nÃ y giÃºp mÃ¬nh hiá»ƒu ráº±ng **scale há»‡ thá»‘ng** khÃ´ng chá»‰ Ä‘Æ¡n giáº£n lÃ  tÄƒng thÃªm sá»‘ lÆ°á»£ng EC2 Instance. Khi á»©ng dá»¥ng phÃ¡t triá»ƒn, há»‡ thá»‘ng cáº§n Ä‘Æ°á»£c chuáº©n bá»‹ vá» kiáº¿n trÃºc, kháº£ nÄƒng chá»‹u lá»—i, kháº£ nÄƒng tá»± phá»¥c há»“i vÃ  kháº£ nÄƒng quan sÃ¡t.

Má»™t há»‡ thá»‘ng cÃ³ thá»ƒ sá»­ dá»¥ng **Auto Scaling Group** Ä‘á»ƒ tá»± Ä‘á»™ng tÄƒng/giáº£m sá»‘ lÆ°á»£ng instance theo táº£i. Tuy nhiÃªn, Ä‘á»ƒ scale Ä‘Ã¡ng tin cáº­y, á»©ng dá»¥ng cÅ©ng cáº§n Ä‘Æ°á»£c triá»ƒn khai trÃªn nhiá»u **Availability Zone**, cÃ³ cÆ¡ cháº¿ health check, giÃ¡m sÃ¡t tÃ i nguyÃªn vÃ  thiáº¿t káº¿ á»©ng dá»¥ng háº¡n cháº¿ phá»¥ thuá»™c vÃ o tráº¡ng thÃ¡i cá»¥c bá»™ cá»§a má»™t server.

## HÃ¬nh áº£nh bÃ i chia sáº»

<img src="/AWS/images/3-BlogsTranslated/blog-2.png" alt="Blog 2 - Scale há»‡ thá»‘ng khÃ´ng chá»‰ lÃ  thÃªm EC2" style="max-width: 100%; border: 1px solid #ddd; border-radius: 8px; margin: 16px 0;" />

## Äiá»u mÃ¬nh há»c Ä‘Æ°á»£c

- TÄƒng sá»‘ lÆ°á»£ng EC2 chá»‰ lÃ  má»™t pháº§n cá»§a bÃ i toÃ¡n scale.
- Auto Scaling cáº§n Ä‘i kÃ¨m health check vÃ  chiáº¿n lÆ°á»£c phÃ¢n phá»‘i táº£i phÃ¹ há»£p.
- Multi-AZ giÃºp há»‡ thá»‘ng cÃ³ kháº£ nÄƒng sáºµn sÃ ng cao hÆ¡n.
- á»¨ng dá»¥ng nÃªn Ä‘Æ°á»£c thiáº¿t káº¿ stateless Ä‘á»ƒ dá»… má»Ÿ rá»™ng.
- Monitoring giÃºp phÃ¡t hiá»‡n bottleneck trÆ°á»›c khi há»‡ thá»‘ng gáº·p lá»—i lá»›n.

## LiÃªn há»‡ vá»›i dá»± Ã¡n SUMMER-STORE

Hiá»‡n táº¡i SUMMER-STORE Ä‘ang cháº¡y backend Spring Boot trÃªn má»™t EC2 Instance. ÄÃ¢y lÃ  mÃ´ hÃ¬nh phÃ¹ há»£p cho mÃ´i trÆ°á»ng demo. Tuy nhiÃªn, náº¿u há»‡ thá»‘ng cÃ³ nhiá»u ngÆ°á»i dÃ¹ng hÆ¡n, hÆ°á»›ng má»Ÿ rá»™ng tiáº¿p theo cÃ³ thá»ƒ lÃ  dÃ¹ng **Application Load Balancer**, **Auto Scaling Group**, triá»ƒn khai backend á»Ÿ nhiá»u Availability Zone vÃ  theo dÃµi há»‡ thá»‘ng báº±ng **Amazon CloudWatch**.

## Link bÃ i chia sáº»

[Facebook group post](https://www.facebook.com/groups/awsstudygroupfcj/?multi_permalinks=2209334513164842&notif_id=1783618764716437&notif_t=feedback_reaction_generic&ref=notif)

