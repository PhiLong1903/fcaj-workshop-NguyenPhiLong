---
title: "Configure JWT Authorizer and CORS"
date: 2026-07-21
weight: 2
chapter: false
pre: " <b> 5.7.2. </b> "
---

#### Create JWT Authorizer

1. In API Gateway, open **Authorizers**.
2. Choose **Create** -> **JWT**.
3. Issuer URL:

```text
https://cognito-idp.<region>.amazonaws.com/<user-pool-id>
```

4. Audience: Cognito App Client ID.
5. Attach authorizer to routes requiring sign-in.

#### CORS

Allowed origins:

```text
http://localhost:5173
https://<your-amplify-domain>
```

Allowed methods:

```text
GET,POST,OPTIONS
```

![Cognito flow](/fcaj-workshop-NguyenPhiLong/images/service-image/5.572.png)
Allowed headers:

```text
content-type,authorization
```
![Cognito flow](/fcaj-workshop-NguyenPhiLong/images/service-image/5.572.png)

#### Error checks

* 401: invalid token or missing authorizer config.
* 403: user lacks permission or admin group is incorrect.
* CORS error: browser blocks the request before Lambda is invoked.
