---
title: "Configure Hosted UI and Groups"
date: 2026-07-21
weight: 2
chapter: false
pre: " <b> 5.3.2. </b> "
---

#### Configure Hosted UI

1. Open the created App Client.
![Cognito flow](/fcaj-workshop-NguyenPhiLong/images/service-image/1_532.png)
2. Open **Login pages**, **Hosted UI**, or **Managed login**.
![Cognito flow](/fcaj-workshop-NguyenPhiLong/images/service-image/2_532.png)
3. Add callback URLs:

```text
http://localhost:5173
https://<your-amplify-domain>
```

4. Add sign-out URLs:

```text
http://localhost:5173
https://<your-amplify-domain>
```

5. Select OAuth scopes:

```text
openid email profile phone
```

#### Create user/admin groups

1. In the User Pool, open **Groups**.
2. Create group user.
3. Create group admin.
4. Select the administrator account and add it to admin.

#### Note

After adding a user to the admin group, sign out and sign in again so the new token contains the group claim. The frontend should only show Admin Console for admins, while admin_api must still validate the token for security.
