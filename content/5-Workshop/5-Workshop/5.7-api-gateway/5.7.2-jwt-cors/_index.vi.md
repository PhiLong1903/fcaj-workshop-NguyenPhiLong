---
title: "Cấu hình JWT Authorizer và CORS"
date: 2026-07-21
weight: 2
chapter: false
pre: " <b> 5.7.2. </b> "
---

#### Tạo JWT Authorizer

1. Trong API Gateway, mở **Authorizers**.
2. Chọn **Create** -> **JWT**.
3. Issuer URL:

```text
https://cognito-idp.<region>.amazonaws.com/<user-pool-id>
```

4. Audience: Cognito App Client ID.
5. Gắn authorizer vào các route cần đăng nhập.

#### CORS

Allowed origins:

```text
http://localhost:5173
https://<amplify-domain-cua-ban>
```

Allowed methods:

```text
GET,POST,OPTIONS
```

Allowed headers:

```text
content-type,authorization
```

#### Kiểm tra lỗi

* Lỗi 401: token không hợp lệ hoặc thiếu authorizer config.
* Lỗi 403: user không đủ quyền hoặc admin group không đúng.
* Lỗi CORS: browser bị chặn trước khi gọi Lambda.
