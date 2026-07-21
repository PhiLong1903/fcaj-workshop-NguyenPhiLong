---
title: "Triển khai Frontend"
date: 2026-07-21
weight: 9
chapter: false
pre: " <b> 5.9. </b> "
---

#### Mục tiêu

Deploy React + Vite frontend để người khác truy cập qua endpoint HTTPS thật.


#### Nơi deploy đề xuất

Project frontend là static React app, nên có thể deploy bằng:

* AWS Amplify Hosting
* Amazon S3 + CloudFront

Trong workshop này dùng **Amplify Hosting** vì thao tác nhanh, dễ kết nối GitHub và tự build từ folder `frontend/`.
