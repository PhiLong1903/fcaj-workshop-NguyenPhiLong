---
title: "Choose Region and create Budget"
date: 2026-07-21
weight: 1
chapter: false
pre: " <b> 5.2.1. </b> "
---

#### Choose Region

Use one Region for the whole project, for example:

```text
ap-southeast-1
```

Using one Region makes it easier for Lambda to call S3, DynamoDB, API Gateway, Bedrock, Polly, and Transcribe without configuration drift.

#### Create AWS Budget

1. Open **Billing and Cost Management**.
![Cognito flow](/images/service-image/billing521.png)
2. Choose **Budgets** -> **Create budget**.

3. Select **Cost budget**.

4. Set a monthly budget, for example 10 USD.

5. Add email alerts at 50%, 80%, and 100%.521.png
![Cognito flow](/images/service-image/521.png)
#### Cost-sensitive services

| Service | Reason |
| --- | --- |
| Amazon Bedrock | CV analysis, question generation, and scoring invoke models. |
| Amazon Transcribe | Charged by audio duration. |
| Amazon Polly | Charged by number of synthesized characters. |
| Amplify Hosting | Charged by build, storage, and data transfer. |
| CloudWatch Logs | Long-retained or excessive logs can create cost. |
