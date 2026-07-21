---
title: "Create Users table"
date: 2026-07-21
weight: 1
chapter: false
pre: " <b> 5.5.1. </b> "
---

#### Create table

1. Open **DynamoDB** -> **Tables** -> **Create table**.
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
6. Create the table.

#### Sample item

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

#### Lambdas using this table

* `profile_api`
* `history_api`
* `admin_api`
