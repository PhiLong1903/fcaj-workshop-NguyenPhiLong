---
title: "Deploy Amazon Cognito"
date: 2026-07-21
weight: 3
chapter: false
pre: " <b> 5.3. </b> "
---

#### Goal

Cognito provides sign-up, sign-in, JWT authentication, and user/admin authorization for Vertex-IntervAI.

![Cognito flow](/fcaj-workshop-NguyenPhiLong/images/5-Workshop/service-image/cogtigo5_3.png)

#### Components to create

| Component | Role |
| --- | --- |
| User Pool | Stores user accounts. |
| App Client | Allows the React frontend to use Cognito Hosted UI. |
| Hosted UI | Cognito-managed sign-in/sign-up pages. |
| Groups | Provides user and admin roles. |
| Callback URL | Frontend URL after successful sign-in. |

After completion, the frontend can redirect users to Hosted UI and receive tokens after sign-in.
