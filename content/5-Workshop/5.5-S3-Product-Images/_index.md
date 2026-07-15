---
title: "Store product images with Amazon S3"
date: 2026-07-01
weight: 5
chapter: false
pre: " <b> 5.5. </b> "
---

# Store product images with Amazon S3

Amazon S3 is used to store product images and media files for the SUMMER-STORE project. Separating media files from the backend makes file management easier, reduces the load on EC2, and allows the frontend to display images conveniently.

#### 1. Create a bucket for product images

Create the Amazon S3 bucket `clothing-store-images-dien0311` to store product images and media files for SUMMER-STORE.

<p class="workshop-img"><img src="/AWS/images/5-Workshop/5.5-S3-Product-Images/5-5-01-s3-images-bucket.png" alt="Create an S3 bucket for product images" style="max-width:100%;height:auto;display:block;margin:1rem auto;border:1px solid #e5e7eb;border-radius:6px;" /></p>
<p style="text-align:center;"><em>Create an S3 bucket for product images</em></p>

#### 2. Upload a test product image

Upload a sample product image to Amazon S3 to test the media storage capability of the bucket.

<p class="workshop-img"><img src="/AWS/images/5-Workshop/5.5-S3-Product-Images/5-5-02-upload-product-image.png" alt="Upload a product image to S3" style="max-width:100%;height:auto;display:block;margin:1rem auto;border:1px solid #e5e7eb;border-radius:6px;" /></p>
<p style="text-align:center;"><em>Upload a product image to S3</em></p>

#### 3. Configure the Bucket Policy

Configure the Bucket Policy to allow public read access to objects in the S3 bucket. This allows the frontend to display product images stored in Amazon S3.

<p class="workshop-img"><img src="/AWS/images/5-Workshop/5.5-S3-Product-Images/5-5-03-bucket-policy.png" alt="Configure public-read bucket policy" style="max-width:100%;height:auto;display:block;margin:1rem auto;border:1px solid #e5e7eb;border-radius:6px;" /></p>
<p style="text-align:center;"><em>Configure public-read bucket policy</em></p>

Example Bucket Policy:

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

