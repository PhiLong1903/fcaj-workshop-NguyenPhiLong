---
title: "Deploy bằng Amplify Hosting"
date: 2026-07-21
weight: 2
chapter: false
pre: " <b> 5.9.2. </b> "
---

#### Các bước deploy

1. Push code lên GitHub.
![Cognito flow](/fcj-workshop-huydat/images/5-Workshop/service-image/224627.png)
2. Vào **AWS Amplify** -> **Host web app**.
![Cognito flow](/fcj-workshop-huydat/images/5-Workshop/service-image/1.5.9.png)
3. Chọn GitHub repository và branch.
4. Vì frontend nằm trong `frontend/`, dùng build setting:

![Cognito flow](/fcj-workshop-huydat/images/5-Workshop/service-image/3.591.png)

5. Thêm environment variables.
![Cognito flow](/fcj-workshop-huydat/images/5-Workshop/service-image/4.592.png)
6. Bấm **Save and deploy**.
7. Copy domain Amplify sau khi deploy thành công.

#### Cập nhật Cognito

Thêm domain Amplify vào:

* Allowed callback URLs
* Allowed sign-out URLs

Sau đó redeploy frontend và test đăng nhập.
