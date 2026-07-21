---
title: "Tạo bucket lưu CV và audio"
date: 2026-07-21
weight: 1
chapter: false
pre: " <b> 5.4.1. </b> "
---

#### Các bước tạo bucket

1. Vào **Amazon S3** -> **Create bucket**.
![Cognito flow](/fcaj-workshop-NguyenPhiLong/images/service-image/1_541.png)
2. Đặt tên bucket duy nhất, ví dụ:

```text
talent-graph-ai-storage-huydat
```

3. Chọn region giống Lambda.
4. Bật **Block all public access**.
![Cognito flow](/fcaj-workshop-NguyenPhiLong/images/service-image/2_541.png)
5. Có thể bật versioning trong giai đoạn test.
6. Tạo bucket.

#### Biến môi trường cần dùng

```text
STORAGE_BUCKET=talent-graph-ai-storage-huydat
VOICE_BUCKET=talent-graph-ai-storage-huydat
```

#### Kiểm tra sau khi tạo

* Bucket không public.
* Lambda role có quyền s3:GetObject, s3:PutObject.
* Upload CV test xong phải thấy object trong prefix cv/.
