---
title: "Test admin, voice, and logs"
date: 2026-07-21
weight: 2
chapter: false
pre: " <b> 5.10.2. </b> "
---

#### Admin flow

* Admin user must belong to group `admin`.
* Normal users cannot see Admin Console.
* Admin can view users, CVs, and interviews.
* Block/delete user, delete interview, and export CSV work correctly.

#### Voice flow

* Website runs on HTTPS for microphone access.
* English questions can play audio.
* A 30-60 second recording returns the main transcript content.
* Switching language does not reset current questions.

#### CloudWatch Logs

Check these log groups:

```text
/aws/lambda/upload_cv
/aws/lambda/analyze_cv
/aws/lambda/create_interview
/aws/lambda/submit_answer
/aws/lambda/transcribe_audio
/aws/lambda/admin_api
```

If API returns 500, check Lambda logs first. If CORS or 401/403 occurs, check API Gateway and Cognito authorizer.
