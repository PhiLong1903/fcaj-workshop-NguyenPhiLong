---
title: "Deploy Amazon API Gateway"
date: 2026-07-21
weight: 7
chapter: false
pre: " <b> 5.7. </b> "
---

#### Goal

API Gateway creates HTTPS endpoints for the frontend to call backend Lambdas. It connects the React app with AWS-side processing services.

![Cognito flow](/fcaj-workshop-NguyenPhiLong/images/service-image/5.7.png)

#### Routes overview

| Method | Route | Lambda |
| --- | --- | --- |
| POST | `/upload_cv` | `upload_cv` |
| POST | `/analyze_cv` | `analyze_cv` |
| GET/POST | `/profile` | `profile_api` |
| GET | `/history` | `history_api` |
| POST | `/interviews` | `create_interview` |
| POST | `/interviews/answer` | `submit_answer` |
| POST | `/voice/question-audio` | `polly_speech` |
| POST | `/voice/transcribe` | `transcribe_audio` |
| ANY | `/admin/{proxy+}` | `admin_api` |
