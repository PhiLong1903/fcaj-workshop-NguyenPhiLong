---
title: "Tạo bảng Users"
date: 2026-07-21
weight: 1
chapter: false
pre: " <b> 5.5.1. </b> "
---

#### Các bước tạo bảng

1. Vào **DynamoDB** -> **Tables** -> **Create table**.
2. Table name:

```text
Users
```

3. Partition key:

```text
userId
```

4. Type: `String`.
5. Billing mode: **On-demand**.
6. Tạo bảng.

#### Dữ liệu mẫu

```json
{
  "userId": "cognito-sub-id",
  "fullName": "Nguyen Huy Dat",
  "email": "user@example.com",
  "phone": "",
  "avatarUrl": "",
  "role": "user",
  "createdAt": "2026-07-21T00:00:00Z"
}
```

#### Lambda sử dụng

* `profile_api`
* `history_api`
* `admin_api`
