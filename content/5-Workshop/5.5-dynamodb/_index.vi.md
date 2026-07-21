---
title: "Triển khai Amazon DynamoDB"
date: 2026-07-21
weight: 5
chapter: false
pre: " <b> 5.5. </b> "
---

#### Mục tiêu

DynamoDB là database chính của hệ thống, lưu hồ sơ người dùng, metadata CV và dữ liệu phỏng vấn.

![Cognito flow](/fcj-workshop-huydat/images/5-Workshop/service-image/5.5.png)

#### Các bảng cần triển khai

| Bảng | Partition key | Sort key | Nội dung |
| --- | --- | --- | --- |
| Users | userId | Không có | Profile, fullname, email, phone, avatar, role. |
| CVs | userId | cvId | File metadata, status, skills, summary, suggested role. |
| Interviews | userId | interviewId | Questions, answers, score, feedback, status, role. |
