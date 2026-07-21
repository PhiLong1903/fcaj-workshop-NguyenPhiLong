---
title: "Dọn dẹp tài nguyên"
date: 2026-07-21
weight: 11
chapter: false
pre: " <b> 5.11. </b> "
---

#### Mục tiêu

Xóa hoặc tắt tài nguyên không còn dùng sau demo để tránh phát sinh chi phí.



#### Checklist dọn dẹp

| Tài nguyên | Cách xử lý |
| --- | --- |
| Amplify app | Delete app nếu không còn public website. |
| API Gateway | Xóa stage/API test không dùng. |
| Lambda | Xóa function test, version/layer dư. |
| S3 | Xóa CV/audio/transcript test; giữ bucket nếu còn demo. |
| DynamoDB | Export dữ liệu cần giữ trước khi xóa bảng. |
| Cognito | Xóa user test, giữ admin/user demo nếu cần. |
| CloudWatch Logs | Giảm retention hoặc xóa log group test. |

#### Kiểm tra cuối

1. Mở Billing dashboard để xem chi phí.
2. Kiểm tra S3 còn file test lớn không.
3. Kiểm tra Lambda/API Gateway còn tài nguyên test không.
4. Lưu lại endpoint, ảnh demo và cấu hình chính để đưa vào báo cáo.
