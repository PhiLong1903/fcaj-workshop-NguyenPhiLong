---
title: "Deploy Frontend"
date: 2026-07-21
weight: 9
chapter: false
pre: " <b> 5.9. </b> "
---

#### Goal

Deploy the React + Vite frontend so other people can access a real HTTPS endpoint.


#### Suggested hosting options

The frontend is a static React app, so it can be deployed with:

* AWS Amplify Hosting
* Amazon S3 + CloudFront

This workshop uses **Amplify Hosting** because it is quick, connects easily to GitHub, and can build from the `frontend/` folder.
