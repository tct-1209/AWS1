---
title: "Translated Blogs"
date: 2026-07-01
weight: 3
chapter: false
pre: " <b> 3. </b> "
---

# Translated Blogs

This section summarizes three AWS-related blog posts that were read, translated, and shared during the internship. The selected topics are closely related to the SUMMER-STORE deployment project: RDS cost optimization, EC2 scalability, and architectural thinking for large-scale Lambda systems.

## Blog list

### [Blog 1 - Optimizing Amazon RDS cost with automated Start/Stop using AWS Lambda](3.1-Blog1/)
This blog explains how to use **Amazon EventBridge Scheduler**, **AWS Lambda**, and an **IAM Role** to automatically start and stop **Amazon RDS** based on a schedule, helping reduce unnecessary database runtime costs.

### [Blog 2 - Scaling a system is not just adding EC2](3.2-Blog2/)
This blog highlights that scaling is not only about adding more EC2 instances. A reliable system should also consider multiple Availability Zones, Auto Scaling, health checks, monitoring, and application design.

### [Blog 3 - Lessons learned from scaling to 1 million Lambda functions](3.3-Blog3/)
This blog summarizes architectural lessons from operating a serverless system at very large scale, including event-driven design, queues, DLQs, service limits, observability, and distributed-system operations.
