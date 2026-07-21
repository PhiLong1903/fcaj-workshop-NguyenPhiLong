---
title: "Cấp quyền Amazon Bedrock"
date: 2026-07-21
weight: 1
chapter: false
pre: " <b> 5.8.1. </b> "
---

#### Cấp quyền model

1. Vào **Amazon Bedrock**.
![Cognito flow](/fcaj-workshop-NguyenPhiLong/images/service-image/1.581.png)
2. Chọn đúng region.
3. Mở **Model access**.
4. Request hoặc enable model Nova Lite nếu tài khoản hỗ trợ.
5. Đợi trạng thái model được cấp quyền.

#### Biến môi trường

```text
BEDROCK_MODEL_ID=apac.amazon.nova-lite-v1:0
BEDROCK_REGION=ap-southeast-1
```

#### Lambda dùng Bedrock

* `analyze_cv`
* `create_interview`
* `submit_answer`

#### Test nhanh

Gọi `analyze_cv` với `userId` và `cvId` đã upload. Nếu Bedrock chưa sẵn sàng, Lambda nên dùng fallback để app vẫn chạy được trong demo.
