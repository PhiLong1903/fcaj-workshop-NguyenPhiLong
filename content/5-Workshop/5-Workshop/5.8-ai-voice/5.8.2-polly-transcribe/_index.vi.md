---
title: "Cấu hình Polly và Transcribe"
date: 2026-07-21
weight: 2
chapter: false
pre: " <b> 5.8.2. </b> "
---

#### Amazon Polly

Polly dùng cho câu hỏi tiếng Anh:

```text
POLLY_VOICE_ID=Joanna
POLLY_ENGINE=standard
```

Lambda `polly_speech` tạo file MP3, lưu vào S3 và trả presigned URL cho frontend phát audio.

#### Amazon Transcribe

Transcribe dùng cho microphone:

```text
TRANSCRIBE_LANGUAGE_CODE=en-US
```

Nếu người dùng chọn tiếng Việt, frontend/backend nên gửi:

```text
vi-VN
```

#### Lưu ý tiếng Việt

Amazon Transcribe hỗ trợ nhận diện tiếng Việt với language code `vi-VN`. Với phần đọc câu hỏi tiếng Việt, Amazon Polly không có voice tiếng Việt phổ biến tương tự voice tiếng Anh, nên có thể dùng browser speech synthesis hoặc provider TTS tiếng Việt khác.

#### Kiểm tra microphone

* Frontend phải chạy trên HTTPS khi deploy thật.
* Audio phải được upload đủ lên S3.
* Transcribe job cần poll đến khi `COMPLETED`.
* Nếu transcript quá ngắn, kiểm tra thời gian ghi âm, khoảng im lặng đầu câu và `languageCode`.
