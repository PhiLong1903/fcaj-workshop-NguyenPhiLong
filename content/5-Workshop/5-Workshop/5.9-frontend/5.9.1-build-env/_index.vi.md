---
title: "Cấu hình build và env frontend"
date: 2026-07-21
weight: 1
chapter: false
pre: " <b> 5.9.1. </b> "
---

#### Build local

```bash
cd frontend
npm install
npm run build
```

Nếu build thành công, Vite sẽ tạo thư mục:

```text
frontend/dist
```

#### Environment variables trên Amplify

Thêm các biến `VITE_...` giống file `.env`, nhưng callback/logout URL phải dùng domain deploy thật.

Ví dụ:

```text
VITE_COGNITO_REDIRECT_URI=https://main.dxxxx.amplifyapp.com
VITE_COGNITO_LOGOUT_URI=https://main.dxxxx.amplifyapp.com
```

#### Lưu ý

Sau khi đổi environment variables trong Amplify, cần redeploy để Vite build lại app với giá trị mới.
