---
title: "Chuẩn bị source code và biến môi trường"
date: 2026-07-21
weight: 2
chapter: false
pre: " <b> 5.2.2. </b> "
---

#### Cấu trúc source code

Project gồm hai phần chính:

```text
frontend/
backend/
```

Trong backend có các Lambda:

![Cognito flow](/fcj-workshop-huydat/images/5-Workshop/service-image/lampda522.png)

#### Biến môi trường frontend

File frontend/.env cần có các endpoint API và Cognito config:

![Cognito flow](/fcj-workshop-huydat/images/5-Workshop/service-image/moitruong522.png)

![Cognito flow](/fcj-workshop-huydat/images/5-Workshop/service-image/apcliaent.png)
#### Kiểm tra local

```bash
cd frontend
npm install
npm run dev
```

Có thể chạy http://localhost:5173 để kiểm tra giao diện trước khi deploy lên Amplify.
