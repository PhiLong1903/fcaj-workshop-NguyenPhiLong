---
title: "Deploy AWS Lambda"
date: 2026-07-21
weight: 6
chapter: false
pre: " <b> 5.6. </b> "
---

#### Goal

Deploy backend Lambdas from the backend/ folder. Each Lambda handles one feature group for easier debugging and scaling.


#### Lambda list

| Lambda | Main route | Role |
| --- | --- | --- |
| `upload_cv` | `POST /upload_cv` | Upload CV to S3 and save metadata. |
| `analyze_cv` | `POST /analyze_cv` | Analyze CV using Bedrock/fallback. |
| `profile_api` | `GET/POST /profile` | Read/write user profile. |
| `history_api` | `GET /history` | Read CV and interview history. |
| `create_interview` | `POST /interviews` | Create interview questions. |
| `submit_answer` | `POST /interviews/answer` | Score answers. |
| `polly_speech` | `POST /voice/question-audio` | Create question audio. |
| `transcribe_audio` | `POST /voice/transcribe` | Convert audio to text. |
| `admin_api` | `/admin/*` | Manage admin data. |
