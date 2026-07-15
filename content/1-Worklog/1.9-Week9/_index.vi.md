---
title: "Worklog Tuáº§n 9"
date: 2026-07-01
weight: 9
chapter: false
pre: " <b> 1.9. </b> "
---

# Worklog Tuáº§n 9: CI/CD triá»ƒn khai á»©ng dá»¥ng vÃ  lÆ°u trá»¯ file doanh nghiá»‡p

**Thá»i gian thá»±c hiá»‡n:** 15/06/2026 - 21/06/2026

## 1. Má»¥c tiÃªu tuáº§n

- TÃ¬m hiá»ƒu CodePipeline, CodeBuild vÃ  CodeDeploy khi deploy á»©ng dá»¥ng lÃªn EC2.
- Náº¯m cÃ¡ch chuáº©n bá»‹ role, artifact, agent vÃ  deployment group.
- TÃ¬m hiá»ƒu cÃ¡c lá»±a chá»n lÆ°u trá»¯ file nhÆ° Storage Gateway vÃ  Amazon FSx.

## 2. Chi tiáº¿t cÃ´ng viá»‡c triá»ƒn khai

| Thá»© | Thá»i gian | Ná»™i dung cÃ´ng viá»‡c |
| --- | --- | --- |
| Thá»© 2 | 15/06/2026 | Äá»c mÃ´ hÃ¬nh CI/CD deploy á»©ng dá»¥ng lÃªn EC2 vá»›i CodePipeline. |
| Thá»© 3 | 16/06/2026 | TÃ¬m hiá»ƒu CodeBuild project, buildspec vÃ  artifact Ä‘áº§u ra. |
| Thá»© 4 | 17/06/2026 | NghiÃªn cá»©u CodeDeploy Application, Deployment Group vÃ  CodeDeploy Agent trÃªn EC2. |
| Thá»© 5 | 18/06/2026 | TÃ¬m hiá»ƒu Storage Gateway Ä‘á»ƒ káº¿t ná»‘i mÃ´i trÆ°á»ng on-premises vá»›i lÆ°u trá»¯ AWS. |
| Thá»© 6 | 19/06/2026 | NghiÃªn cá»©u Amazon FSx for Windows File Server vÃ  use case chia sáº» file qua SMB. |

## 3. Káº¿t quáº£ Ä‘áº¡t Ä‘Æ°á»£c

- Hiá»ƒu quy trÃ¬nh tá»± Ä‘á»™ng hÃ³a build/deploy lÃªn EC2.
- Biáº¿t vai trÃ² cá»§a tá»«ng thÃ nh pháº§n trong pipeline.
- Má»Ÿ rá»™ng kiáº¿n thá»©c vá» lÆ°u trá»¯ file trong mÃ´i trÆ°á»ng doanh nghiá»‡p.

## 4. Nguá»“n tÃ i liá»‡u tham kháº£o

| Nguá»“n | ÄÆ°á»ng dáº«n | Ná»™i dung tham kháº£o |
| --- | --- | --- |
| 000023 - Deploy to EC2 with CodePipeline | [https://000023.awsstudygroup.com/](https://000023.awsstudygroup.com/) | CodePipeline, CodeBuild, CodeDeploy |
| 000024 - Storage Gateway | [https://000024.awsstudygroup.com/](https://000024.awsstudygroup.com/) | File Storage Gateway |
| 000025 - Amazon FSx for Windows File Server | [https://000025.awsstudygroup.com/](https://000025.awsstudygroup.com/) | Managed Windows file shares |

