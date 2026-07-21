---
title: "Enable Amazon Bedrock model access"
date: 2026-07-21
weight: 1
chapter: false
pre: " <b> 5.8.1. </b> "
---

#### Enable model access

1. Open **Amazon Bedrock**.
![Cognito flow](/fcaj-workshop-NguyenPhiLong/images/service-image/1.581.png)
2. Select the correct Region.
3. Open **Model access**.
4. Request or enable Nova Lite if available for the account.
5. Wait until model access is granted.

#### Environment variables

```text
BEDROCK_MODEL_ID=apac.amazon.nova-lite-v1:0
BEDROCK_REGION=ap-southeast-1
```

#### Lambdas using Bedrock

* `analyze_cv`
* `create_interview`
* `submit_answer`

#### Quick test

Call `analyze_cv` with an uploaded `userId` and `cvId`. If Bedrock is not ready, Lambda should use fallback logic so the app can still run during demo.
