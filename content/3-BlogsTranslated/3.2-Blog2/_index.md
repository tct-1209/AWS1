---
title: "Blog 2 - Scaling a system is not just adding EC2"
date: 2026-07-01
weight: 2
chapter: false
pre: " <b> 3.2. </b> "
---

# AWS Compute Blog | Scaling a system is not just adding EC2

## Main content

This blog helped me understand that **system scaling** is not simply adding more EC2 instances. As an application grows, the architecture must also consider reliability, fault tolerance, self-healing, and observability.

A system can use an **Auto Scaling Group** to automatically increase or decrease the number of instances based on traffic. However, reliable scaling also requires deployment across multiple **Availability Zones**, health checks, resource monitoring, and application design that avoids strong dependency on the local state of a single server.

## Shared post screenshot

<img src="/aws/images/3-BlogsTranslated/blog-2.png" alt="Blog 2 - Scaling a system is not just adding EC2" style="max-width: 100%; border: 1px solid #ddd; border-radius: 8px; margin: 16px 0;" />

## What I learned

- Adding EC2 instances is only one part of the scaling problem.
- Auto Scaling should be combined with health checks and a suitable traffic distribution strategy.
- Multi-AZ deployment improves system availability.
- Applications should be designed to be stateless for easier scaling.
- Monitoring helps identify bottlenecks before they become serious issues.

## Relation to the SUMMER-STORE project

At the moment, SUMMER-STORE runs the Spring Boot backend on a single EC2 instance, which is suitable for a demo environment. If the system grows, the next improvements could include **Application Load Balancer**, **Auto Scaling Group**, multi-AZ backend deployment, and monitoring with **Amazon CloudWatch**.

## Shared post link

[Facebook group post](https://www.facebook.com/groups/awsstudygroupfcj/?multi_permalinks=2209334513164842&notif_id=1783618764716437&notif_t=feedback_reaction_generic&ref=notif)
