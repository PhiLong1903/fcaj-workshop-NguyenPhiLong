---
title: "Deploy voice và admin Lambda"
date: 2026-07-21
weight: 3
chapter: false
pre: " <b> 5.6.3. </b> "
---

#### Deploy `polly_speech`

```text
backend/polly_speech/lambda_function.py
```
![Cognito flow](/fcj-workshop-huydat/images/5-Workshop/service-image/1.563.png)
Biến môi trường:

![Cognito flow](/fcj-workshop-huydat/images/5-Workshop/service-image/2.563.png)

IAM cần `polly:SynthesizeSpeech`, `s3:PutObject`.

#### Deploy `transcribe_audio`

```text
backend/transcribe_audio/lambda_function.py
```
![Cognito flow](/fcj-workshop-huydat/images/5-Workshop/service-image/3.563.png)
Biến môi trường:

![Cognito flow](/fcj-workshop-huydat/images/5-Workshop/service-image/4.563.png)

IAM cần `transcribe:StartTranscriptionJob`, `transcribe:GetTranscriptionJob`, `s3:PutObject`, `s3:GetObject`.

#### Deploy `admin_api`

```text
backend/admin_api/lambda_function.py
```
![Cognito flow](/fcj-workshop-huydat/images/5-Workshop/service-image/5.563.png)
Admin API cần quyền đọc/ghi phù hợp trên `Users`, `CVs`, `Interviews`. Nếu có chức năng khóa user bằng Cognito, Lambda role cần thêm quyền Cognito như `cognito-idp:AdminDisableUser` và `cognito-idp:AdminEnableUser`.
