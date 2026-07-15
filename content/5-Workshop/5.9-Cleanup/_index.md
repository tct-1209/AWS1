---
title: "Clean up resources"
date: 2026-07-01
weight: 9
chapter: false
pre: " <b> 5.9. </b> "
---

# Clean up resources

After finishing the demo or report, clean up or stop AWS resources to avoid unwanted costs.

#### Resources to review

| Resource | Recommended action |
|---|---|
| Amazon EC2 | Stop the instance when not in use |
| Amazon RDS | Stop the database when not demoing/testing |
| Elastic IP | Keep it if EC2 is still used; release it if no longer needed |
| Amazon S3 Frontend Bucket | Keep it if the website still needs to be public |
| Amazon S3 Images Bucket | Delete objects/bucket if no longer needed |
| AWS Budgets | Keep the budget to receive cost alerts |

#### Start/stop EC2 with AWS CLI

```powershell
$INSTANCE_ID = "i-07d1af0954de7115d"
$REGION = "us-east-1"
$PROFILE = "clothing-store-v2"

aws ec2 stop-instances --instance-ids $INSTANCE_ID --region $REGION --profile $PROFILE
aws ec2 start-instances --instance-ids $INSTANCE_ID --region $REGION --profile $PROFILE
```

#### Startup/shutdown order for demo

When starting a demo:

```text
Start RDS → Start EC2 → check backend service → access the website
```

When not using the system:

```text
Stop EC2 → Stop RDS
```

{{% notice warning %}}
RDS may automatically restart after a temporary stop period. Check Billing, Credits, and Budgets regularly to control costs.
{{% /notice %}}
