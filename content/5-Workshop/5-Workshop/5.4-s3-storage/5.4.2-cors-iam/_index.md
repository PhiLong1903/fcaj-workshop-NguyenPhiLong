---
title: "Configure S3 CORS and IAM"
date: 2026-07-21
weight: 2
chapter: false
pre: " <b> 5.4.2. </b> "
---

#### CORS for presigned URL

If Admin Console or frontend opens files with presigned URLs, add bucket CORS:

```json
[
  {
    "AllowedHeaders": ["*"],
    "AllowedMethods": ["GET", "PUT", "POST"],
    "AllowedOrigins": [
      "http://localhost:5173",
      "https://<your-amplify-domain>"
    ],
    "ExposeHeaders": ["ETag"]
  }
]
```

#### Minimum IAM policy for Lambda

```json
{
  "Effect": "Allow",
  "Action": ["s3:GetObject", "s3:PutObject"],
  "Resource": "arn:aws:s3:::talent-graph-ai-storage-huydat/*"
}
```

If Lambda needs to list objects:

```json
{
  "Effect": "Allow",
  "Action": ["s3:ListBucket"],
  "Resource": "arn:aws:s3:::talent-graph-ai-storage-huydat"
}
```
