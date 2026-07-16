---
title: "Blog 1 - T?i uu chi ph� Amazon RDS b?ng c�ch t? d?ng Start/Stop v?i AWS Lambda"
date: 2026-07-01
weight: 1
chapter: false
pre: " <b> 3.1. </b> "
---

# AWS Database Blog | T?i uu chi ph� Amazon RDS b?ng c�ch t? d?ng Start/Stop v?i AWS Lambda

## N?i dung ch�nh

Trong qu� tr�nh t�m hi?u AWS, b�i vi?t n�y gi�p m�nh nh?n ra r?ng t?i uu chi ph� l� m?t ph?n r?t quan tr?ng khi tri?n khai h? th?ng l�n cloud. V?i **Amazon RDS**, n?u database v?n ho?t d?ng trong th?i gian kh�ng s? d?ng, h? th?ng v?n c� th? ph�t sinh chi ph� kh�ng c?n thi?t.

Gi?i ph�p du?c d? c?p l� s? d?ng **Amazon EventBridge Scheduler** d? k�ch ho?t c�c **AWS Lambda Function** theo l?ch. M?t Lambda function d�ng d? stop RDS v�o cu?i ng�y l�m vi?c, function c�n l?i d�ng d? start RDS v�o d?u ng�y h�m sau. C�c Lambda function n�y c?n du?c g�n **IAM Role** ph� h?p d? c� quy?n th?c hi?n thao t�c v?i RDS.

## Ki?n tr�c tham kh?o

<img src="/AWS/images/3-BlogsTranslated/blog-1.png" alt="Blog 1 - Auto Start Stop Amazon RDS with AWS Lambda" style="max-width: 100%; border: 1px solid #ddd; border-radius: 8px; margin: 16px 0;" />

## �i?u m�nh h?c du?c

- T�i nguy�n cloud n�n du?c b?t/t?t theo nhu c?u s? d?ng th?c t?.
- EventBridge Scheduler ph� h?p d? t? d?ng h�a c�c t�c v? ch?y theo l?ch.
- Lambda c� th? x? l� c�c t�c v? v?n h�nh nh?, kh�ng c?n duy tr� server ri�ng.
- IAM Role c?n du?c ph�n quy?n d�ng d? Lambda c� th? start/stop RDS an to�n.
- V?i m�i tru?ng h?c t?p ho?c demo, t? d?ng h�a vi?c start/stop c� th? gi�p ti?t ki?m credit.

## Li�n h? v?i d? �n SUMMER-STORE

Trong d? �n SUMMER-STORE, m�nh s? d?ng **Amazon RDS SQL Server** l�m database ch�nh. Khi kh�ng demo ho?c kh�ng test h? th?ng, vi?c stop RDS v� EC2 gi�p gi?m chi ph� s? d?ng AWS. B�i blog n�y g?i � m?t hu?ng m? r?ng t?t hon trong tuong lai: t? d?ng h�a vi?c b?t/t?t database thay v� thao t�c th? c�ng tr�n AWS Console.

## Link b�i chia s?

[Facebook post](https://www.facebook.com/share/p/1BZeHedGDc/)







