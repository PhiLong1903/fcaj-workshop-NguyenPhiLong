---
title: "Configure frontend build and env"
date: 2026-07-21
weight: 1
chapter: false
pre: " <b> 5.9.1. </b> "
---

#### Local build

```bash
cd frontend
npm install
npm run build
```

If build succeeds, Vite creates:

```text
frontend/dist
```

#### Amplify environment variables

Add the same `VITE_...` variables as `.env`, but callback/logout URLs must use the real deployed domain.

Example:

```text
VITE_COGNITO_REDIRECT_URI=https://main.dxxxx.amplifyapp.com
VITE_COGNITO_LOGOUT_URI=https://main.dxxxx.amplifyapp.com
```

#### Note

After changing environment variables in Amplify, redeploy so Vite rebuilds the app with the new values.
