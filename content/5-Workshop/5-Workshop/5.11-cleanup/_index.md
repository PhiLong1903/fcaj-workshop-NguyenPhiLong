---
title: "Clean up resources"
date: 2026-07-21
weight: 11
chapter: false
pre: " <b> 5.11. </b> "
---

#### Goal

Delete or disable unused resources after the demo to avoid unnecessary cost.


#### Cleanup checklist

| Resource | Action |
| --- | --- |
| Amplify app | Delete the app if the public website is no longer needed. |
| API Gateway | Delete unused test stages/APIs. |
| Lambda | Delete test functions, unused versions/layers. |
| S3 | Delete test CV/audio/transcript objects; keep the bucket if demo continues. |
| DynamoDB | Export needed data before deleting tables. |
| Cognito | Delete test users, keep demo/admin users if needed. |
| CloudWatch Logs | Reduce retention or delete test log groups. |

#### Final check

1. Open Billing dashboard to review cost.
2. Check whether S3 still has large test files.
3. Check whether Lambda/API Gateway still has test resources.
4. Save endpoints, demo images, and key configuration for the report.
