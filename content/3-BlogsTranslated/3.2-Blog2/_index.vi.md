---
title: "Blog 2 - Scale h? th?ng kh�ng ch? l� th�m EC2"
date: 2026-07-01
weight: 2
chapter: false
pre: " <b> 3.2. </b> "
---

# AWS Compute Blog | Scale h? th?ng kh�ng ch? l� th�m EC2

## N?i dung ch�nh

B�i blog n�y gi�p m�nh hi?u r?ng **scale h? th?ng** kh�ng ch? don gi?n l� tang th�m s? lu?ng EC2 Instance. Khi ?ng d?ng ph�t tri?n, h? th?ng c?n du?c chu?n b? v? ki?n tr�c, kh? nang ch?u l?i, kh? nang t? ph?c h?i v� kh? nang quan s�t.

M?t h? th?ng c� th? s? d?ng **Auto Scaling Group** d? t? d?ng tang/gi?m s? lu?ng instance theo t?i. Tuy nhi�n, d? scale d�ng tin c?y, ?ng d?ng cung c?n du?c tri?n khai tr�n nhi?u **Availability Zone**, c� co ch? health check, gi�m s�t t�i nguy�n v� thi?t k? ?ng d?ng h?n ch? ph? thu?c v�o tr?ng th�i c?c b? c?a m?t server.

## H�nh ?nh b�i chia s?

<img src="/AWS/images/3-BlogsTranslated/blog-2.png" alt="Blog 2 - Scale h? th?ng kh�ng ch? l� th�m EC2" style="max-width: 100%; border: 1px solid #ddd; border-radius: 8px; margin: 16px 0;" />

## �i?u m�nh h?c du?c

- Tang s? lu?ng EC2 ch? l� m?t ph?n c?a b�i to�n scale.
- Auto Scaling c?n di k�m health check v� chi?n lu?c ph�n ph?i t?i ph� h?p.
- Multi-AZ gi�p h? th?ng c� kh? nang s?n s�ng cao hon.
- ?ng d?ng n�n du?c thi?t k? stateless d? d? m? r?ng.
- Monitoring gi�p ph�t hi?n bottleneck tru?c khi h? th?ng g?p l?i l?n.

## Li�n h? v?i d? �n SUMMER-STORE

Hi?n t?i SUMMER-STORE dang ch?y backend Spring Boot tr�n m?t EC2 Instance. ��y l� m� h�nh ph� h?p cho m�i tru?ng demo. Tuy nhi�n, n?u h? th?ng c� nhi?u ngu?i d�ng hon, hu?ng m? r?ng ti?p theo c� th? l� d�ng **Application Load Balancer**, **Auto Scaling Group**, tri?n khai backend ? nhi?u Availability Zone v� theo d�i h? th?ng b?ng **Amazon CloudWatch**.

## Link b�i chia s?

[Facebook group post](https://www.facebook.com/groups/awsstudygroupfcj/?multi_permalinks=2209334513164842&notif_id=1783618764716437&notif_t=feedback_reaction_generic&ref=notif)








