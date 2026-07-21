---
title: "Cấu hình Hosted UI và Groups"
date: 2026-07-21
weight: 2
chapter: false
pre: " <b> 5.3.2. </b> "
---

#### Cấu hình Hosted UI

1. Mở App Client vừa tạo.
![Cognito flow](/fcaj-workshop-NguyenPhiLong/images/service-image/1_532.png)
2. Vào phần **Login pages**, **Hosted UI** hoặc **Managed login**.
![Cognito flow](/fcaj-workshop-NguyenPhiLong/images/service-image/2_532.png)
3. Thêm callback URL:

```text
http://localhost:5173
https://<amplify-domain-cua-ban>
```

4. Thêm sign-out URL:

```text
http://localhost:5173
https://<amplify-domain-cua-ban>
```

5. Chọn OAuth scopes:

```text
openid email profile phone
```

#### Tạo group user/admin

1. Trong User Pool, mở **Groups**.
2. Tạo group user.
3. Tạo group admin.
4. Chọn tài khoản quản trị và thêm vào group admin.

#### Lưu ý

Sau khi thêm user vào group admin, cần đăng xuất và đăng nhập lại để token mới có claim group. Frontend chỉ nên hiển thị Admin Console cho user có group admin, nhưng backend admin_api vẫn cần kiểm tra token để bảo mật.
