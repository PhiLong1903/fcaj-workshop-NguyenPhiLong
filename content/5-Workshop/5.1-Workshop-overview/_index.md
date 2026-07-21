---
title: "Overview"
date: 2026-07-21
weight: 1
chapter: false
pre: " <b> 5.1. </b> "
---

#### Goal

This project aims to build an intelligent interview training system based on personal CVs. The system uses AWS Serverless services combined with AI to analyze CVs, generate interview questions based on roles, support written or voice responses, evaluate answers, and record training history. Through this, users can improve their interview skills, identify strengths and weaknesses, and better prepare for the recruitment process.

![Cognito flow](/fcj-workshop-huydat/images/5-Workshop/service-image/bieudo.jpeg)

#### Main features

| Feature | Description |
| --- | --- |
| Authentication | Users sign up/sign in through Amazon Cognito Hosted UI. |
| CV upload | Frontend sends base64 CV to Lambda; Lambda stores the file in S3. |
| CV analysis | Lambda reads CV from S3 and analyzes it with Amazon Bedrock Nova Lite or fallback logic. |
| AI Interview | The system creates role/CV-based questions; question count is selectable from frontend. |
| Scoring | Lambda receives answers and returns score, feedback, and improvement advice. |
| Voice | Polly creates question audio; Transcribe converts answer audio to text. |
| History/Result | Users review CV history, interview history, final score, and advice. |
| Admin Console | Admins manage users, CVs, interviews, review queue, audit log, and CSV export. |

#### Integrated AWS services

* Amazon Cognito
* Amazon S3
* Amazon DynamoDB
* AWS Lambda
* Amazon API Gateway
* Amazon Bedrock
* Amazon Polly
* Amazon Transcribe
* Amazon CloudWatch
* AWS Amplify Hosting

#### Deployment flow

1. Prepare Region, budget, source code, and environment variables.
2. Create Cognito for user authentication.
3. Create S3 and DynamoDB for storage/database.
4. Deploy Lambda backend.
5. Create API Gateway routes and JWT Authorizer.
6. Enable Bedrock/Polly/Transcribe for AI and voice.
7. Deploy frontend with Amplify Hosting.
8. Test the full user flow and admin flow.
