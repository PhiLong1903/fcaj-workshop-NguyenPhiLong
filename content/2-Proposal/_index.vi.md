---
title: "Bản đề xuất"
date: 2024-01-01
weight: 2
chapter: false
pre: " <b> 2. </b> "
---

# Đề xuất Vertex-IntervAI / Talent Graph AI
## Nền tảng phỏng vấn AI trên AWS Serverless

### 1. Tóm tắt dự án

Vertex-IntervAI, còn được gọi là Talent Graph AI, là một ứng dụng web hỗ trợ ứng viên luyện phỏng vấn dựa trên chính CV của họ. Người dùng tải CV lên, hệ thống lưu trữ CV an toàn, phân tích nội dung bằng AI, tạo câu hỏi phỏng vấn theo CV và role đã chọn, cho phép trả lời bằng văn bản hoặc giọng nói, chấm điểm từng câu trả lời, sau đó trả về kết quả kèm điểm số, nhận xét và lời khuyên cải thiện.

Dự án sử dụng frontend React + Vite và backend AWS Serverless. Backend được xây dựng bằng Amazon API Gateway, AWS Lambda, Amazon S3, Amazon DynamoDB, Amazon Cognito, Amazon Bedrock, Amazon Polly, Amazon Transcribe, Amazon CloudWatch và Amazon SES cho hướng phát triển gửi email phản hồi.

Hiện tại dự án đã có luồng chính cho người dùng: trang đăng nhập bằng Cognito, dashboard, upload CV, phân tích CV, chọn role phỏng vấn, chọn số câu hỏi, phỏng vấn với AI, chấm điểm câu trả lời, trang kết quả, lịch sử, profile, settings, chuyển đổi ngôn ngữ/giao diện và admin console. Các phần cần hoàn thiện thêm nằm ở xác thực thật bằng JWT, kiểm tra IAM/CORS, test đầy đủ voice flow, đồng bộ history đa thiết bị và triển khai production.

### 2. Bài toán cần giải quyết
#### Thực trạng
Nhiều sinh viên và ứng viên mới đi làm luyện phỏng vấn bằng danh sách câu hỏi chung, nên nội dung luyện tập thường không bám sát CV, kỹ năng, dự án, kinh nghiệm và vị trí ứng tuyển thật. Mock interview thủ công cũng tốn thời gian và khó lặp lại nhiều lần.

#### Giải pháp đề xuất
Vertex-IntervAI giải quyết bài toán này bằng cách biến CV thành một quy trình luyện phỏng vấn cá nhân hóa:

- Phân tích CV để lấy kỹ năng, kinh nghiệm, học vấn, dự án và gợi ý role phù hợp.
- Cho phép ứng viên chọn role AI như software engineer, data analyst, AI engineer, cloud engineer hoặc role được gợi ý từ CV.
- Tạo số lượng câu hỏi có thể cấu hình, mặc định là 5 và tối thiểu là 2.
- Hỗ trợ trả lời bằng text hoặc voice.
- Chấm điểm từng câu trả lời và đưa ra nhận xét, gợi ý cải thiện.
- Lưu lịch sử phỏng vấn để người dùng xem lại.
- Cung cấp admin console để quản lý users, CVs, interviews, review queue, audit log, export CSV và feedback email.
### 3. Mục tiêu đồ án
Đồ án hướng đến việc xây dựng một hệ thống luyện phỏng vấn AI có tính thực tế với các mục tiêu:

- Xây dựng ứng dụng web hoàn chỉnh cho upload CV, luyện phỏng vấn AI, xem kết quả, xem lịch sử và quản lý hồ sơ.
- Áp dụng kiến trúc AWS Serverless để giảm công việc quản trị hạ tầng và hỗ trợ mở rộng linh hoạt.
Sử dụng Amazon Bedrock để phân tích CV, tạo câu hỏi phỏng vấn và đánh giá câu trả lời.
- Hỗ trợ luyện phỏng vấn bằng giọng nói với Amazon Polly và Amazon Transcribe.
- Lưu trữ thông tin người dùng, metadata CV, phiên phỏng vấn và kết quả theo cấu trúc rõ ràng.
- Cung cấp trang admin để theo dõi và quản lý dữ liệu vận hành.
- Xây dựng workshop triển khai từng bước trên AWS.


### 4. Kiến trúc giải pháp

![Arch](/fcaj-workshop-NguyenPhiLong/images/Arch.jpg)

### 5. Dịch vụ AWS sử dụng

- **Amazon Cognito** Đăng ký, đăng nhập, Hosted UI, xác thực JWT và phân quyền user/admin
- **Amazon DynamoDB** Lưu người dùng, metadata CV, phiên phỏng vấn, câu trả lời, điểm số và lịch sử.
- **Amazon S3** Lưu file CV, audio câu hỏi, audio câu trả lời và transcript.
- **AWS Lambda** Chạy backend cho upload CV, phân tích CV, profile, tạo phỏng vấn, chấm điểm, voice, history và admin.
- **Amazon API Gateway** Cung cấp REST API, cấu hình CORS và bảo vệ route bằng JWT authorizer.
- **Amazon Bedrock** Phân tích CV, tạo câu hỏi phỏng vấn, đánh giá câu trả lời và đưa ra gợi ý cải thiện.
- **Amazon Polly** Chuyển câu hỏi phỏng vấn thành audio.
- **Amazon Transcribe** Chuyển câu trả lời bằng giọng nói thành văn bản.
- **Amazon CloudWatch Logs** 	Lưu log và hỗ trợ debug Lambda/API Gateway.
- **AWS Amplify Hosting** Build và triển khai frontend React + Vite.

### 6. Triển khai kỹ thuật

Workshop được chia theo từng giai đoạn triển khai dịch vụ:

1. Chuẩn bị AWS Region, cảnh báo ngân sách, source code và biến môi trường.
2. Tạo Cognito User Pool, App Client, Hosted UI domain, callback URL, logout URL và nhóm user/admin.
3. Tạo S3 bucket cho CV và audio, cấu hình CORS và IAM permission.
4. Tạo DynamoDB tables gồm Users, CVs và Interviews.
5. Deploy Lambda functions cho CV, profile, history, interview, voice và admin.
6. Tạo API Gateway routes, kết nối Lambda integration, cấu hình CORS và JWT authorization.
7. Bật quyền truy cập model Amazon Bedrock và kết nối vào các Lambda liên quan đến AI.
8. Cấu hình Amazon Polly và Amazon Transcribe cho tính năng voice.
9. Cấu hình biến môi trường frontend .env và deploy React + Vite bằng Amplify Hosting.
10. Kiểm thử luồng người dùng, luồng admin, voice, trang kết quả và lịch sử.
11. Dọn dẹp tài nguyên sau workshop để tránh phát sinh chi phí không cần thiết.

#### Trạng thái hiện tại

| Hạng mục | Trạng thái |
| --- | --- |
| Upload CV lên S3 | Đã làm |
| Lưu metadata CV vào DynamoDB | Đã làm |
| Phân tích CV bằng Bedrock/fallback | Đã làm |
| Profile GET/POST | Đã làm |
| Tạo câu hỏi phỏng vấn | Đã làm |
| Chấm điểm câu tr

### 7. Timeline và mốc hoàn thành

- **Phase 1 - Khởi tạo dự án và thiết kế kiến trúc**: Phân tích yêu cầu, tạo React project, xây routing và layout cơ bản, thiết kế DynamoDB schema, chuẩn bị S3 lưu CV, xác định workflow AI và lập checklist kiến trúc AWS.
- **Phase 2 - Đăng nhập, upload CV và lưu trữ**: Hoàn thiện Login UI, tích hợp Cognito Hosted UI, làm giao diện upload CV kéo thả, viết Lambda `upload_cv`, lưu file vào S3, lưu metadata vào DynamoDB và cấu hình callback/logout URL.
- **Phase 3 - Phân tích CV và Dashboard**: Hoàn thiện Dashboard, viết Lambda `analyze_cv`, đọc CV từ S3, phân tích CV bằng Bedrock/Nova Lite, lưu skills/projects/experience/certificates và bảo vệ API bằng Cognito JWT authorizer.
- **Phase 4 - AI Interview và chấm điểm câu trả lời**: Xây giao diện AI Interview, tạo session phỏng vấn, sinh câu hỏi theo CV và role, lưu câu trả lời, chấm điểm, trả feedback, gợi ý câu trả lời tốt hơn và tính điểm tổng.
- **Phase 5 - Voice, History, Profile, Settings và Admin**: Xây trang History, Profile, Settings, viết `history_api` và `profile_api`, tích hợp Polly/Transcribe cho voice, xây Admin Console, export CSV và chuẩn bị workflow feedback email.
- **Phase 6 - Kiểm thử, deploy, tài liệu và demo**: Polish UI, kiểm thử responsive, kiểm tra API Gateway/Lambda/DynamoDB/IAM/CORS, cải thiện prompt và scoring, tổng hợp deploy guide, chụp màn hình, hoàn thiện worklog và checklist demo.

### 8. Ước tính chi phí

Dự án được thiết kế cho môi trường đồ án/demo nên chi phí ban đầu thấp nếu lượng người dùng nhỏ. Các phần ảnh hưởng chi phí nhiều nhất là Bedrock inference, Transcribe minutes, Polly characters, S3 storage, DynamoDB read/write capacity, API Gateway requests và Lambda invocations.

Hướng chi phí dự kiến:

- **Demo traffic thấp**: chủ yếu nằm trong free-tier hoặc chi phí thấp, trừ Bedrock/voice usage.
- **Giai đoạn test nhiều**: chi phí tăng theo số lần tạo câu hỏi, chấm điểm, tạo audio và transcribe.
- **Production**: thêm CloudFront, WAF, monitoring, backup và SES production email sau khi account đủ điều kiện.

Cách kiểm soát chi phí:

- Giới hạn số câu hỏi mặc định.
- Chỉ lưu audio/transcript cần thiết.
- Dùng DynamoDB on-demand cho traffic demo khó dự đoán.
- Tạo AWS Budgets alerts.
- Đặt thời gian lưu CloudWatch Logs hợp lý.

### 9. Đánh giá rủi ro

| Rủi ro | Ảnh hưởng | Cách giảm thiểu |
| --- | --- | --- |
| Sai callback/logout URL Cognito | Người dùng không đăng nhập được | Đồng bộ URL trong Cognito và frontend `.env` |
| Thiếu CORS | Frontend không gọi được API | Kiểm tra từng route bằng DevTools và API Gateway CORS |
| IAM thiếu hoặc quá rộng | Lambda lỗi hoặc mất an toàn | Tách policy least privilege cho từng Lambda |
| Bedrock model không sẵn sàng | Không phân tích/chấm điểm được | Giữ fallback và xử lý lỗi rõ ràng |
| Polly voice không hợp tiếng Việt | Audio tiếng Việt đọc sai | Chọn voice theo ngôn ngữ và dùng browser speech fallback khi cần |
| Transcribe sai language code | Nhận diện giọng nói sai | Gửi language code theo ngôn ngữ UI |
| SES sandbox | Chỉ gửi email đến địa chỉ đã verify | Xin SES production access trước khi bật production email |
| CloudFront/WAF bị giới hạn account | Chưa triển khai production static hosting | Dùng local/Vite hoặc S3 hosting trong giai đoạn chờ verified |

### 10. Kết quả kỳ vọng

Sau khi hoàn thành, Vertex-IntervAI có thể cung cấp một quy trình luyện phỏng vấn AI hoàn chỉnh: người dùng đăng nhập, upload CV, nhận phân tích AI, luyện phỏng vấn, trả lời bằng văn bản hoặc giọng nói, xem điểm số và feedback, đồng thời xem lại lịch sử luyện tập. Workshop cũng tạo ra bộ tài liệu có thể tái sử dụng để triển khai hệ thống tương tự trên AWS Serverless.