---
title: "Triển khai Amazon Cognito"
date: 2026-07-21
weight: 3
chapter: false
pre: " <b> 5.3. </b> "
---

#### Mục tiêu

Cognito cung cấp đăng ký, đăng nhập, xác thực JWT và phân quyền user/admin cho Vertex-IntervAI.

![Cognito flow](/fcaj-workshop-NguyenPhiLong/images/5-Workshop/service-image/cogtigo5_3.png)

#### Thành phần cần tạo

| Thành phần | Vai trò |
| --- | --- |
| User Pool | Lưu tài khoản người dùng. |
| App Client | Cho phép frontend React dùng Cognito Hosted UI. |
| Hosted UI | Trang đăng nhập/đăng ký do Cognito quản lý. |
| Groups | Phân quyền user và admin. |
| Callback URL | URL frontend sau khi đăng nhập thành công. |

Sau khi hoàn tất, frontend có thể chuyển người dùng sang Hosted UI và nhận token sau khi đăng nhập.
