---
title: "Blog 3 - Lessons learned from scaling to 1 million Lambda functions"
date: 2026-07-01
weight: 3
chapter: false
pre: " <b> 3.3. </b> "
---

# AWS Architecture Blog | Lessons learned from scaling to 1 million Lambda functions

## N?i dung ch�nh

B�i vi?t n�y n�i v? nh?ng b�i h?c khi m?t h? th?ng serverless ph�t tri?n t?i quy m� r?t l?n, v?i hon 1 tri?u **AWS Lambda functions**. �i?u m�nh ?n tu?ng l� v?n d? scale kh�ng ch? n?m ? vi?c tang t�i nguy�n, m� c�n n?m ? c�ch thi?t k? ki?n tr�c v� qu?n l� d? ph?c t?p c?a h? th?ng.

C�c th�nh ph?n nhu **Amazon EventBridge**, **Amazon SQS**, **AWS Lambda** v� **DLQ** thu?ng du?c s? d?ng d? x�y d?ng lu?ng x? l� b?t d?ng b?. Khi h? th?ng l?n d?n, vi?c s? d?ng h�ng d?i, co ch? retry, dead-letter queue v� ph�n t�ch tr�ch nhi?m gi?a c�c th�nh ph?n gi�p h? th?ng ?n d?nh hon.

## H�nh ?nh b�i chia s?

<img src="/AWS/images/3-BlogsTranslated/blog-3.png" alt="Blog 3 - Lessons learned from scaling to 1 million Lambda functions" style="max-width: 100%; border: 1px solid #ddd; border-radius: 8px; margin: 16px 0;" />

## �i?u m�nh h?c du?c

- Scale ? quy m� l?n c?n tu duy ki?n tr�c, kh�ng ch? tang t�i nguy�n.
- Event-driven architecture gi�p c�c th�nh ph?n k?t n?i r?i r?c v� d? m? r?ng hon.
- SQS v� DLQ gi�p h? th?ng x? l� l?i t?t hon trong c�c lu?ng b?t d?ng b?.
- C?n ch� � service quotas, logging, monitoring v� c�ch t? ch?c t�i nguy�n.
- Khi h? th?ng ph�t tri?n, vi?c chu?n h�a pattern ki?n tr�c gi�p gi?m r?i ro v?n h�nh.

## Li�n h? v?i d? �n SUMMER-STORE

D? �n SUMMER-STORE hi?n d�ng ki?n tr�c don gi?n v?i frontend tr�n S3, backend tr�n EC2 v� database tr�n RDS. Tuy nhi�n, c�c b�i h?c t? h? th?ng Lambda quy m� l?n v?n r?t h?u �ch. Trong tuong lai, nh?ng t�c v? nhu x? l� don h�ng, g?i th�ng b�o, x? l� thanh to�n ho?c d?ng b? d? li?u c� th? du?c t�ch th�nh c�c lu?ng event-driven d? h? th?ng linh ho?t v� d? m? r?ng hon.

## Link b�i chia s?

File Word hi?n chua cung c?p link b�i chia s? cho Blog 3.





