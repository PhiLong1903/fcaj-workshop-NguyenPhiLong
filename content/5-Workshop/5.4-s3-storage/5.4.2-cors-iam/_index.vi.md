---
title: "Cấu hình CORS và IAM cho S3"
date: 2026-07-21
weight: 2
chapter: false
pre: " <b> 5.4.2. </b> "
---

#### CORS cho presigned URL

Nếu Admin Console hoặc frontend mở file bằng presigned URL, thêm CORS cho bucket:

```json
[
  {
    "AllowedHeaders": ["*"],
    "AllowedMethods": ["GET", "PUT", "POST"],
    "AllowedOrigins": [
      "http://localhost:5173",
      "https://<amplify-domain-cua-ban>"
    ],
    "ExposeHeaders": ["ETag"]
  }
]
```

#### IAM policy tối thiểu cho Lambda

```json
{
  "Effect": "Allow",
  "Action": ["s3:GetObject", "s3:PutObject"],
  "Resource": "arn:aws:s3:::talent-graph-ai-storage-huydat/*"
}
```

Nếu Lambda cần liệt kê object:

```json
{
  "Effect": "Allow",
  "Action": ["s3:ListBucket"],
  "Resource": "arn:aws:s3:::talent-graph-ai-storage-huydat"
}
```
