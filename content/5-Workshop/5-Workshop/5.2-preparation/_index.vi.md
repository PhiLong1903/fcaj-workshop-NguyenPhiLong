---
title: "Chuẩn bị môi trường"
date: 2026-07-21
weight: 2
chapter: false
pre: " <b> 5.2. </b> "
---

#### Mục tiêu

Chuẩn bị AWS account, region, budget, source code và thông tin cấu hình trước khi triển khai từng service.


#### Checklist chuẩn bị

| Hạng mục | Kết quả cần có |
| --- | --- |
| AWS account | Có quyền tạo Cognito, S3, DynamoDB, Lambda, API Gateway, Bedrock, Polly, Transcribe, Amplify. |
| Region | Dùng thống nhất một region, ví dụ ap-southeast-1. |
| Budget | Có cảnh báo chi phí để kiểm soát Bedrock/Transcribe/Amplify. |
| Source code | Repo có frontend/ và backend/. |
| API test tool | Postman hoặc curl để test API Gateway. |
| Browser | Chrome/Edge để test Cognito, microphone và UI responsive. |

#### Thông tin cần ghi lại

* AWS Account ID
* Region
* S3 bucket name
* DynamoDB table names
* Lambda function names
* API Gateway invoke URL
* Cognito User Pool ID
* Cognito App Client ID
* Amplify domain
