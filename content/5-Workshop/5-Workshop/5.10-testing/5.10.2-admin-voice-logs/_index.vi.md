---
title: "Kiểm thử admin, voice và logs"
date: 2026-07-21
weight: 2
chapter: false
pre: " <b> 5.10.2. </b> "
---

#### Admin flow

* Admin user phải thuộc group `admin`.
* User thường không thấy Admin Console.
* Admin xem được users, CVs, interviews.
* Chức năng khóa/xóa user, xóa interview, export CSV hoạt động đúng.

#### Voice flow

* Website chạy HTTPS để dùng microphone.
* Câu hỏi tiếng Anh phát được audio.
* Ghi âm dài 30-60 giây và transcript trả đủ nội dung chính.
* Đổi ngôn ngữ không được reset câu hỏi hiện tại.

#### CloudWatch Logs

Kiểm tra các log group:

```text
/aws/lambda/upload_cv
/aws/lambda/analyze_cv
/aws/lambda/create_interview
/aws/lambda/submit_answer
/aws/lambda/transcribe_audio
/aws/lambda/admin_api
```

Nếu API lỗi 500, xem Lambda log trước. Nếu lỗi CORS hoặc 401/403, xem API Gateway và Cognito authorizer.
