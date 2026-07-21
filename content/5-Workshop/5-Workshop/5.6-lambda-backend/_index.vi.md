---
title: "Triển khai AWS Lambda"
date: 2026-07-21
weight: 6
chapter: false
pre: " <b> 5.6. </b> "
---

#### Mục tiêu

Triển khai các Lambda backend trong thư mục backend/. Mỗi Lambda xử lý một nhóm chức năng riêng để dễ debug và mở rộng.


#### Danh sách Lambda

| Lambda | Route chính | Vai trò |
| --- | --- | --- |
| `upload_cv` | `POST /upload_cv` | Upload CV lên S3, lưu metadata. |
| `analyze_cv` | `POST /analyze_cv` | Phân tích CV bằng Bedrock/fallback. |
| `profile_api` | `GET/POST /profile` | Đọc/ghi hồ sơ người dùng. |
| `history_api` | `GET /history` | Đọc lịch sử CV và interview. |
| `create_interview` | `POST /interviews` | Tạo câu hỏi phỏng vấn. |
| `submit_answer` | `POST /interviews/answer` | Chấm điểm câu trả lời. |
| `polly_speech` | `POST /voice/question-audio` | Tạo audio câu hỏi. |
| `transcribe_audio` | `POST /voice/transcribe` | Chuyển audio thành text. |
| `admin_api` | `/admin/*` | Quản trị dữ liệu. |
