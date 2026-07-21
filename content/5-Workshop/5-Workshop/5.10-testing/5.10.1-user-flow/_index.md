---
title: "Test user flow"
date: 2026-07-21
weight: 1
chapter: false
pre: " <b> 5.10.1. </b> "
---

#### Checklist

| Step | Action | Expected result |
| --- | --- | --- |
| 1 | Sign in with Cognito | Returns to frontend and displays the correct user. |
| 2 | Upload CV | S3 has the file, DynamoDB `CVs` has metadata. |
| 3 | Analyze CV | CV has skills, summary, suggested role. |
| 4 | Create interview | DynamoDB `Interviews` has questions. |
| 5 | Answer questions | API returns score and feedback. |
| 6 | Complete | Result shows final score and general feedback. |
| 7 | Open History | CV/interview history exists and detail view works. |

#### If data appears as a new user

Check `userId` from the Cognito token. If the old data used demo localStorage `user_demo_001`, but deployment uses Cognito `sub`, old data will not match automatically. Migrate data or use the matching userId in DynamoDB.
