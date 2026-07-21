---
title: "Tạo bảng CVs và Interviews"
date: 2026-07-21
weight: 2
chapter: false
pre: " <b> 5.5.2. </b> "
---

#### Tạo bảng CVs

| Cấu hình | Giá trị |
| --- | --- |
| Table name | CVs |
| Partition key | userId |
| Sort key | cvId |
| Billing mode | On-demand |

#### Tạo bảng Interviews

| Cấu hình | Giá trị |
| --- | --- |
| Table name | Interviews |
| Partition key | userId |
| Sort key | interviewId |
| Billing mode | On-demand |

#### Kiểm tra dữ liệu sau khi chạy app

* Upload CV xong phải có item trong CVs.
* Analyze CV xong item CVs phải có skills, summary, status.
* Tạo interview xong phải có item trong Interviews.
* Trả lời câu hỏi xong Interviews phải có answers, attempts, score hoặc finalScore.

#### Biến môi trường Lambda

```text
CVS_TABLE=CVs
INTERVIEWS_TABLE=Interviews
```
