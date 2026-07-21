---
title: "Deploy with Amplify Hosting"
date: 2026-07-21
weight: 2
chapter: false
pre: " <b> 5.9.2. </b> "
---

#### Deployment steps

1. Push code to GitHub.
![Cognito flow](/fcaj-workshop-NguyenPhiLong/images/service-image/224627.png)
2. Open **AWS Amplify** -> **Host web app**.

![Cognito flow](/fcaj-workshop-NguyenPhiLong/images/service-image/1.5.9.png)
3. Select GitHub repository and branch.
4. Because the frontend is inside `frontend/`, use this build setting:

![Cognito flow](/fcaj-workshop-NguyenPhiLong/images/service-image/3.591.png)

5. Add environment variables.
![Cognito flow](/fcaj-workshop-NguyenPhiLong/images/service-image/4.592.png)

6. Click **Save and deploy**.
7. Copy the Amplify domain after deployment succeeds.


#### Update Cognito

Add the Amplify domain to:

* Allowed callback URLs
* Allowed sign-out URLs

Then redeploy frontend and test sign-in.
