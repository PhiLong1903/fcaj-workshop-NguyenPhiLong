---
title: "Create User Pool and App Client"
date: 2026-07-21
weight: 1
chapter: false
pre: " <b> 5.3.1. </b> "
---

#### Create User Pool

1. Open **Amazon Cognito** -> **User pools**.

![Cognito flow](/fcj-workshop-huydat/images/5-Workshop/service-image/1_531.png)

2. Choose **Create user pool**.

3. For Define your application options, choose **Traditional web application**.

![Cognito flow](/fcj-workshop-huydat/images/5-Workshop/service-image/2_531.png)

4. Enable required attributes:
   * email
   * name
   * phone_number

![Cognito flow](/fcj-workshop-huydat/images/5-Workshop/service-image/3_531.png)

5. Use email verification.

![Cognito flow](/fcj-workshop-huydat/images/5-Workshop/service-image/3_531.png)

6. Create the User Pool.

#### Create App Client

1. In the User Pool, open **App clients**.
![Cognito flow](/fcj-workshop-huydat/images/5-Workshop/service-image/4_531.png)
2. Choose **Create app client**.
![Cognito flow](/fcj-workshop-huydat/images/5-Workshop/service-image/5.531.png)
3. Select a web application client type.
4. Do not enable client secret for a React SPA.
5. Copy the **App client ID** for:

```text
VITE_COGNITO_CLIENT_ID=<app-client-id>
```

#### Check

* User Pool ID looks like `ap-southeast-1_xxxxx`.
* App Client ID is saved.
* Email verification works for new users.
