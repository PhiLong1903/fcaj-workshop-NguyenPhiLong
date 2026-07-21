---
title: "Giới thiệu"
date: 2026-07-21
weight: 1
chapter: false
pre: " <b> 5.1. </b> "
---

#### Mục tiêu

Đồ án hướng đến việc xây dựng hệ thống hỗ trợ luyện phỏng vấn thông minh dựa trên CV cá nhân. Hệ thống sử dụng các dịch vụ AWS Serverless kết hợp với AI để phân tích CV, tạo bộ câu hỏi phỏng vấn theo vai trò, hỗ trợ trả lời bằng văn bản hoặc giọng nói, đánh giá câu trả lời và lưu lại lịch sử luyện tập. Qua đó, người dùng có thể cải thiện kỹ năng phỏng vấn, nhận biết điểm mạnh, điểm yếu và chuẩn bị tốt hơn cho quá trình tuyển dụng.

![Cognito flow](/static/images/service-image/bieudo.jpeg)

#### Các chức năng chính

| Chức năng | Mô tả |
| --- | --- |
| Đăng nhập | Người dùng đăng ký/đăng nhập bằng Amazon Cognito Hosted UI. |
| Upload CV | Frontend gửi CV dạng base64 đến Lambda, Lambda lưu file vào S3. |
| Phân tích CV | Lambda đọc CV từ S3 và phân tích bằng Amazon Bedrock Nova Lite hoặc fallback logic. |
| AI Interview | Hệ thống tạo câu hỏi theo CV/role, số câu hỏi có thể chọn từ frontend. |
| Chấm điểm | Lambda nhận câu trả lời, dùng AI/fallback để trả điểm, feedback và gợi ý cải thiện. |
| Voice | Polly tạo audio câu hỏi, Transcribe chuyển audio câu trả lời thành text. |
| History/Result | Người dùng xem lịch sử CV, lịch sử phỏng vấn, final score và lời khuyên. |
| Admin Console | Admin quản lý users, CVs, interviews, review queue, audit log và export CSV. |

#### Dịch vụ AWS tích hợp

* Amazon Cognito
* Amazon S3
* Amazon DynamoDB
* AWS Lambda
* Amazon API Gateway
* Amazon Bedrock
* Amazon Polly
* Amazon Transcribe
* Amazon CloudWatch
* AWS Amplify Hosting

#### Luồng triển khai

1. Chuẩn bị region, budget, source code và biến môi trường.
2. Tạo Cognito để xác thực người dùng.
3. Tạo S3 và DynamoDB làm storage/database.
4. Deploy Lambda backend.
5. Tạo API Gateway routes và JWT Authorizer.
6. Bật Bedrock/Polly/Transcribe cho AI và voice.
7. Deploy frontend bằng Amplify Hosting.
8. Kiểm thử toàn bộ user flow và admin flow.
