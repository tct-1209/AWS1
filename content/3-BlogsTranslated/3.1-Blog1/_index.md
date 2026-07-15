---
title: "Blog 1 - Optimizing Amazon RDS cost with automated Start/Stop using AWS Lambda"
date: 2026-07-01
weight: 1
chapter: false
pre: " <b> 3.1. </b> "
---

# AWS Database Blog | Optimizing Amazon RDS cost with automated Start/Stop using AWS Lambda

## Main content

This blog helped me understand that cost optimization is an important part of deploying systems to the cloud. With **Amazon RDS**, if a database keeps running when it is not needed, it can still generate unnecessary costs.

The proposed solution uses **Amazon EventBridge Scheduler** to trigger **AWS Lambda functions** on a fixed schedule. One Lambda function stops the RDS database at the end of the working day, while another Lambda function starts it again at the beginning of the next working day. These functions require a suitable **IAM Role** to perform RDS operations securely.

## Reference architecture

<img src="/aws/images/3-BlogsTranslated/blog-1.png" alt="Blog 1 - Auto Start Stop Amazon RDS with AWS Lambda" style="max-width: 100%; border: 1px solid #ddd; border-radius: 8px; margin: 16px 0;" />

## What I learned

- Cloud resources should run based on actual usage needs.
- EventBridge Scheduler is useful for automating scheduled operations.
- Lambda can handle small operational tasks without maintaining a dedicated server.
- IAM Roles must be configured correctly so Lambda can start and stop RDS safely.
- For a learning or demo environment, scheduled start/stop can help save AWS credits.

## Relation to the SUMMER-STORE project

In the SUMMER-STORE project, **Amazon RDS for SQL Server** is used as the main database. When the system is not being demonstrated or tested, stopping RDS and EC2 helps reduce AWS costs. This blog suggests a future improvement: automating database start/stop instead of doing it manually in the AWS Console.

## Shared post link

[Facebook post](https://www.facebook.com/share/p/1BZeHedGDc/)
