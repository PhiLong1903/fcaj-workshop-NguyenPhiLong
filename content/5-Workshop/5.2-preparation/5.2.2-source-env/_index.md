---
title: "Prepare source code and environment variables"
date: 2026-07-21
weight: 2
chapter: false
pre: " <b> 5.2.2. </b> "
---

#### Source code structure

The project has two main parts:

```text
frontend/
backend/
```

The backend/ folder contains these Lambdas:

![Cognito flow](/fcj-workshop-huydat/images/5-Workshop/service-image/lampda522.png)

#### Frontend environment variables

frontend/.env needs API endpoints and Cognito config:

![Cognito flow](/fcj-workshop-huydat/images/5-Workshop/service-image/moitruong522.png)

![Cognito flow](/fcj-workshop-huydat/images/5-Workshop/service-image/apcliaent.png)

#### Local check

```bash
cd frontend
npm install
npm run dev
```

Can run `http://localhost:5173` to verify the UI before deploying to Amplify.
