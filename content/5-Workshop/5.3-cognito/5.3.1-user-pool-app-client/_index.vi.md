---
title: "Tạo User Pool và App Client"
date: 2026-07-21
weight: 1
chapter: false
pre: " <b> 5.3.1. </b> "
---

#### Tạo User Pool

1. Vào **Amazon Cognito** -> **User pools**.
![Cognito flow](/fcaj-workshop-NguyenPhiLong/images/5-Workshop/service-image/1_531.png)
2. Chọn **Create user pool**.

3. Ở phần Define your application, chọn **Traditional web application**.
![Cognito flow](/fcaj-workshop-NguyenPhiLong/images/5-Workshop/service-image/2_531.png)
4. Bật các thuộc tính cần dùng:
   * email
   * name`
   * phone_number
![Cognito flow](/fcaj-workshop-NguyenPhiLong/images/5-Workshop/service-image/3_531.png)

5. Chọn gửi mã xác nhận qua email.
![Cognito flow](/fcaj-workshop-NguyenPhiLong/images/5-Workshop/service-image/2_531.png)

6. Tạo User Pool.

#### Tạo App Client

1. Trong User Pool, mở **App clients**.
![Cognito flow](/fcaj-workshop-NguyenPhiLong/images/5-Workshop/service-image/4_531.png)
2. Chọn **Create app client**.
![Cognito flow](/fcaj-workshop-NguyenPhiLong/images/5-Workshop/service-image/5.531.png)
3. Chọn app type cho web application.

4. Không bật client secret nếu frontend là SPA React.

5. Copy lại **App client ID** để dùng cho biến:

```text
VITE_COGNITO_CLIENT_ID=<app-client-id>
```

#### Kiểm tra

* User Pool ID có dạng ap-southeast-1_xxxxx.
* App Client ID đã được lưu lại.
* Email verification hoạt động khi tạo user mới.
