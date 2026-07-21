---
title: "Triển khai Amazon API Gateway"
date: 2026-07-21
weight: 7
chapter: false
pre: " <b> 5.7. </b> "
---

#### Mục tiêu

API Gateway tạo endpoint HTTPS để frontend gọi Lambda backend. Đây là lớp kết nối giữa React app và các service xử lý phía AWS.

![Cognito flow](/fcj-workshop-huydat/images/5-Workshop/service-image/5.7.png)

#### Routes tổng quan

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
