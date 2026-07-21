---
title: "Tạo routes và Lambda integrations"
date: 2026-07-21
weight: 1
chapter: false
pre: " <b> 5.7.1. </b> "
---

#### Các bước tạo API

1. Vào **Amazon API Gateway**.
![Cognito flow](/fcaj-workshop-NguyenPhiLong/images/service-image/1.571.png)
2. Chọn **Create API**.
![Cognito flow](/fcaj-workshop-NguyenPhiLong/images/service-image/1.571.png)
3. Chọn **HTTP API**.
![Cognito flow](/fcaj-workshop-NguyenPhiLong/images/service-image/2.671.png)
4. Tạo integration đến từng Lambda.
5. Tạo route theo bảng ở mục `5.7`.
6. Tạo stage, ví dụ:

```text
default
```

7. Copy invoke URL để dùng cho frontend.

#### Ví dụ endpoint sau deploy

```text
https://<api-id>.execute-api.ap-southeast-1.amazonaws.com/default/upload_cv
```

#### Kiểm tra route

* Mỗi route phải trỏ đúng Lambda.
* Lambda permission phải cho API Gateway invoke function.
* Stage đã deploy hoặc bật auto deploy.
