---
title: "Deploy upload_cv, profile_api, history_api"
date: 2026-07-21
weight: 1
chapter: false
pre: " <b> 5.6.1. </b> "
---

#### Deploy `upload_cv`

1. Tạo Lambda `upload_cv`.
![Cognito flow](/fcj-workshop-huydat/images/5-Workshop/service-image/1_561.png)
2. Runtime: Python 3.12.
![Cognito flow](/fcj-workshop-huydat/images/5-Workshop/service-image/1_561.png)
3. Copy code từ:

```text
backend/upload_cv/lambda_function.py
```
![Cognito flow](/fcj-workshop-huydat/images/5-Workshop/service-image/2_561.png)
4. Thêm biến môi trường:

![Cognito flow](/fcj-workshop-huydat/images/5-Workshop/service-image/3_561.png)

5. IAM cần có `s3:PutObject`, `dynamodb:PutItem`.

#### Deploy `profile_api`

```text
backend/profile_api/lambda_function.py
```
![Cognito flow](/fcj-workshop-huydat/images/5-Workshop/service-image/5.561.png)

Biến môi trường:

![Cognito flow](/fcj-workshop-huydat/images/5-Workshop/service-image/6.561.png)


IAM cần có `dynamodb:GetItem`, `dynamodb:PutItem`, `dynamodb:UpdateItem`.

#### Deploy `history_api`

```text
backend/history_api/lambda_function.py
```

Biến môi trường:

![Cognito flow](/fcj-workshop-huydat/images/5-Workshop/service-image/7.561.png)

IAM cần có `dynamodb:Query` trên hai bảng `CVs` và `Interviews`.
