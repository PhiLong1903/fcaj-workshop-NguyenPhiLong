---
title: "Deploy analyze_cv, create_interview, submit_answer"
date: 2026-07-21
weight: 2
chapter: false
pre: " <b> 5.6.2. </b> "
---

#### Deploy `analyze_cv`

1. Tạo Lambda `analyze_cv`.
2. Copy code từ:

```text
backend/analyze_cv/lambda_function.py
```
![Cognito flow](/fcaj-workshop-NguyenPhiLong/images/service-image/1.562.png)
3. Thêm biến môi trường:

![Cognito flow](/fcaj-workshop-NguyenPhiLong/images/service-image/2.562.png)

4. Thêm layer đọc PDF nếu cần:

```text
backend/analyze_cv/analyze_cv_pypdf_layer.zip
```

#### Deploy `create_interview`

```text
backend/create_interview/lambda_function.py
```
![Cognito flow](/fcaj-workshop-NguyenPhiLong/images/service-image/3.562.png)
Biến môi trường:

![Cognito flow](/fcaj-workshop-NguyenPhiLong/images/service-image/4.562.png)

#### Deploy `submit_answer`

```text
backend/submit_answer/lambda_function.py
```
![Cognito flow](/fcaj-workshop-NguyenPhiLong/images/service-image/5.562.png)
Biến môi trường:

![Cognito flow](/fcaj-workshop-NguyenPhiLong/images/service-image/6.562.png)

IAM của các Lambda này cần `bedrock:InvokeModel` và quyền đọc/ghi DynamoDB tương ứng.
