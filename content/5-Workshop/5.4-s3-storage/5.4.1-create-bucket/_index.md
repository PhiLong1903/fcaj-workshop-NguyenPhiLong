---
title: "Create bucket for CV and audio"
date: 2026-07-21
weight: 1
chapter: false
pre: " <b> 5.4.1. </b> "
---

#### Create bucket

1. Open **Amazon S3** -> **Create bucket**

![Cognito flow](/fcj-workshop-huydat/images/5-Workshop/service-image/1_541.png)
2. Use a unique bucket name, for example:

```text
talent-graph-ai-storage-huydat
```

3. Choose the same Region as Lambda.
4. Enable **Block all public access**.
![Cognito flow](/fcj-workshop-huydat/images/5-Workshop/service-image/2_541.png)

5. Versioning can be enabled during testing.
6. Create the bucket.

#### Required environment variables

```text
STORAGE_BUCKET=talent-graph-ai-storage-huydat
VOICE_BUCKET=talent-graph-ai-storage-huydat
```

#### Checks

* Bucket is not public.
* Lambda role has s3:GetObject, s3:PutObject.
* After testing CV upload, an object appears under cv/.
