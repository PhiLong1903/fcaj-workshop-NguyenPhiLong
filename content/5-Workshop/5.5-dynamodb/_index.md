---
title: "Deploy Amazon DynamoDB"
date: 2026-07-21
weight: 5
chapter: false
pre: " <b> 5.5. </b> "
---

#### Goal

DynamoDB is the main database of the system, storing user profiles, CV metadata, and interview data.


![Cognito flow](/fcaj-workshop-NguyenPhiLong/images/5-Workshop/service-image/5.5.png)

#### Tables to deploy

| Table | Partition key | Sort key | Content |
| --- | --- | --- | --- |
| Users | userId | None | Profile, fullname, email, phone, avatar, role. |
| CVs | userId | cvId | File metadata, status, skills, summary, suggested role. |
| Interviews | userId | interviewId | Questions, answers, score, feedback, status, role. |
