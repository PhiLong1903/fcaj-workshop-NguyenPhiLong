---
title: "Kiểm thử user flow"
date: 2026-07-21
weight: 1
chapter: false
pre: " <b> 5.10.1. </b> "
---

#### Checklist

| Bước | Hành động | Kết quả mong đợi |
| --- | --- | --- |
| 1 | Đăng nhập bằng Cognito | Quay về frontend và hiển thị đúng user. |
| 2 | Upload CV | S3 có file, DynamoDB `CVs` có metadata. |
| 3 | Analyze CV | CV có skills, summary, suggested role. |
| 4 | Tạo interview | DynamoDB `Interviews` có questions. |
| 5 | Trả lời câu hỏi | API trả score và feedback. |
| 6 | Hoàn thành | Result hiển thị final score và general feedback. |
| 7 | Mở History | Có lịch sử CV/interview và xem chi tiết được. |

#### Nếu dữ liệu bị thành user mới

Kiểm tra `userId` lấy từ Cognito token. Nếu trước đây dùng demo localStorage `user_demo_001`, còn khi deploy dùng Cognito `sub`, dữ liệu cũ sẽ không tự khớp. Cần migrate dữ liệu hoặc dùng đúng userId trong DynamoDB.
