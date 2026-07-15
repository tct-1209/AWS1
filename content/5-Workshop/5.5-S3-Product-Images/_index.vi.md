---
title: "LÆ°u trá»¯ áº£nh sáº£n pháº©m báº±ng Amazon S3"
date: 2026-07-01
weight: 5
chapter: false
pre: " <b> 5.5. </b> "
---

# LÆ°u trá»¯ áº£nh sáº£n pháº©m báº±ng Amazon S3

Amazon S3 Ä‘Æ°á»£c sá»­ dá»¥ng Ä‘á»ƒ lÆ°u trá»¯ áº£nh sáº£n pháº©m vÃ  cÃ¡c file media cho dá»± Ã¡n SUMMER-STORE. Viá»‡c tÃ¡ch áº£nh ra khá»i backend giÃºp há»‡ thá»‘ng dá»… quáº£n lÃ½ file, giáº£m táº£i cho EC2 vÃ  thuáº­n tiá»‡n khi frontend cáº§n hiá»ƒn thá»‹ áº£nh.

#### 1. Táº¡o bucket lÆ°u áº£nh sáº£n pháº©m

Táº¡o thÃ nh cÃ´ng Amazon S3 Bucket `clothing-store-images-dien0311` Ä‘á»ƒ lÆ°u trá»¯ áº£nh sáº£n pháº©m vÃ  cÃ¡c file media cho dá»± Ã¡n SUMMER-STORE.

<p class="workshop-img"><img src="/AWS/images/5-Workshop/5.5-S3-Product-Images/5-5-01-s3-images-bucket.png" alt="Táº¡o S3 bucket lÆ°u áº£nh sáº£n pháº©m" style="max-width:100%;height:auto;display:block;margin:1rem auto;border:1px solid #e5e7eb;border-radius:6px;" /></p>
<p style="text-align:center;"><em>Táº¡o S3 bucket lÆ°u áº£nh sáº£n pháº©m</em></p>

#### 2. Upload thá»­ áº£nh sáº£n pháº©m

Upload thá»­ áº£nh sáº£n pháº©m lÃªn Amazon S3 Ä‘á»ƒ kiá»ƒm tra kháº£ nÄƒng lÆ°u trá»¯ media cá»§a bucket.

<p class="workshop-img"><img src="/AWS/images/5-Workshop/5.5-S3-Product-Images/5-5-02-upload-product-image.png" alt="Upload áº£nh sáº£n pháº©m lÃªn S3" style="max-width:100%;height:auto;display:block;margin:1rem auto;border:1px solid #e5e7eb;border-radius:6px;" /></p>
<p style="text-align:center;"><em>Upload áº£nh sáº£n pháº©m lÃªn S3</em></p>

#### 3. Cáº¥u hÃ¬nh Bucket Policy

Cáº¥u hÃ¬nh Bucket Policy cho phÃ©p public read cÃ¡c object trong S3 Bucket. Nhá» Ä‘Ã³ frontend cÃ³ thá»ƒ hiá»ƒn thá»‹ áº£nh sáº£n pháº©m Ä‘Æ°á»£c lÆ°u trá»¯ trÃªn Amazon S3.

<p class="workshop-img"><img src="/AWS/images/5-Workshop/5.5-S3-Product-Images/5-5-03-bucket-policy.png" alt="Cáº¥u hÃ¬nh bucket policy public read" style="max-width:100%;height:auto;display:block;margin:1rem auto;border:1px solid #e5e7eb;border-radius:6px;" /></p>
<p style="text-align:center;"><em>Cáº¥u hÃ¬nh bucket policy public read</em></p>

VÃ­ dá»¥ Bucket Policy:

```json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Sid": "PublicReadGetObject",
      "Effect": "Allow",
      "Principal": "*",
      "Action": "s3:GetObject",
      "Resource": "arn:aws:s3:::clothing-store-images-dien0311/*"
    }
  ]
}
```

