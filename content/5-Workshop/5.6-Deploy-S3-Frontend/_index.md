---
title: "Deploy the React frontend with Amazon S3 Static Website Hosting"
date: 2026-07-01
weight: 6
chapter: false
pre: " <b> 5.6. </b> "
---

# Deploy the React frontend with Amazon S3 Static Website Hosting

The React/Vite frontend is built into static files and uploaded to Amazon S3. S3 Static Website Hosting allows the website to be accessed through the S3 website endpoint.

#### 1. Build the React/Vite frontend

Build the React frontend into static files to prepare it for deployment to Amazon S3.

<p class="workshop-img"><img src="/AWS/images/5-Workshop/5.6-Deploy-S3-Frontend/5-6-01-frontend-source.png" alt="Frontend source before build" style="max-width:100%;height:auto;display:block;margin:1rem auto;border:1px solid #e5e7eb;border-radius:6px;" /></p>
<p style="text-align:center;"><em>Frontend source before build</em></p>

Example build commands:

```bash
npm install
npm run build
```

#### 2. Create an S3 bucket for the frontend

Create a separate S3 bucket to store the static files generated from the React frontend build.

<p class="workshop-img"><img src="/AWS/images/5-Workshop/5.6-Deploy-S3-Frontend/5-6-02-s3-frontend-bucket.png" alt="Create the S3 frontend bucket" style="max-width:100%;height:auto;display:block;margin:1rem auto;border:1px solid #e5e7eb;border-radius:6px;" /></p>
<p style="text-align:center;"><em>Create the S3 frontend bucket</em></p>

Project frontend bucket:

```text
clothing-store-frontend-dien0311
```

#### 3. Upload static files to S3

Upload all static files from the React frontend build to Amazon S3. The `assets` and `images` folders are kept so that the website can load JavaScript, CSS, and images correctly.

<p class="workshop-img"><img src="/AWS/images/5-Workshop/5.6-Deploy-S3-Frontend/5-6-03-upload-static-files.png" alt="Upload frontend static files to S3" style="max-width:100%;height:auto;display:block;margin:1rem auto;border:1px solid #e5e7eb;border-radius:6px;" /></p>
<p style="text-align:center;"><em>Upload frontend static files to S3</em></p>

#### 4. Enable Static Website Hosting

Enable Static Website Hosting for the S3 bucket to deploy the React frontend as a static website. The `index.html` file is used as the main page of the application.

<p class="workshop-img"><img src="/AWS/images/5-Workshop/5.6-Deploy-S3-Frontend/5-6-04-static-website-hosting.png" alt="Enable Static Website Hosting for S3" style="max-width:100%;height:auto;display:block;margin:1rem auto;border:1px solid #e5e7eb;border-radius:6px;" /></p>
<p style="text-align:center;"><em>Enable Static Website Hosting for S3</em></p>

Basic configuration:

```text
Index document: index.html
Error document: index.html
```

#### 5. Test the website after deployment

The React frontend is built and deployed successfully to Amazon S3 Static Website Hosting. The website can be accessed through the S3 website endpoint and loads HTML, CSS, JavaScript, and images correctly.

<p class="workshop-img"><img src="/AWS/images/5-Workshop/5.6-Deploy-S3-Frontend/5-6-05-frontend-s3-success.png" alt="SUMMER-STORE frontend running on S3" style="max-width:100%;height:auto;display:block;margin:1rem auto;border:1px solid #e5e7eb;border-radius:6px;" /></p>
<p style="text-align:center;"><em>SUMMER-STORE frontend running on S3</em></p>

{{% notice note %}}
In the current project scope, the frontend is deployed directly with S3 Static Website Hosting. CloudFront and Route 53 can be added later if a custom domain, HTTPS, or CDN is required.
{{% /notice %}}

