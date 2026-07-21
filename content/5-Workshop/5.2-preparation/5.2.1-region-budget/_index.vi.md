---
title: "Chọn Region và tạo Budget"
date: 2026-07-21
weight: 1
chapter: false
pre: " <b> 5.2.1. </b> "
---

#### Chọn Region

Nên dùng một region thống nhất cho toàn bộ đồ án, ví dụ:

```text
ap-southeast-1
```

Khi dùng cùng region, Lambda sẽ dễ gọi S3, DynamoDB, API Gateway, Bedrock, Polly và Transcribe hơn, đồng thời giảm lỗi cấu hình nhầm region.

#### Tạo AWS Budget

1. Vào **Billing and Cost Management**.
![Cognito flow](/fcj-workshop-huydat/images/5-Workshop/service-image/billing521.png)
2. Chọn **Budgets** -> **Create budget**.

3. Chọn **Cost budget**.

4. Đặt ngân sách tháng, ví dụ 10 USD.

5. Thêm email nhận cảnh báo ở mức 50%, 80% và 100%.
![Cognito flow](/fcj-workshop-huydat/images/5-Workshop/service-image/521.png)
#### Dịch vụ cần chú ý chi phí

| Service | Lý do |
| --- | --- |
| Amazon Bedrock | Mỗi lần phân tích CV, sinh câu hỏi, chấm điểm đều gọi model. |
| Amazon Transcribe | Tính chi phí theo thời lượng audio. |
| Amazon Polly | Tính theo số ký tự chuyển thành giọng nói. |
| Amplify Hosting | Tính theo build, storage và data transfer. |
| CloudWatch Logs | Log lưu lâu hoặc quá nhiều có thể phát sinh chi phí. |
