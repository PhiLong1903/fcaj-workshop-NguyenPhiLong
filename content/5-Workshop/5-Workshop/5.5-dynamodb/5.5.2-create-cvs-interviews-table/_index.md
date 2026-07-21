---
title: "Create CVs and Interviews tables"
date: 2026-07-21
weight: 2
chapter: false
pre: " <b> 5.5.2. </b> "
---

#### Create CVs table

| Config | Value |
| --- | --- |
| Table name | CVs |
| Partition key | userId |
| Sort key | cvId |
| Billing mode | On-demand |

#### Create Interviews table

| Config | Value |
| --- | --- |
| Table name | Interviews |
| Partition key | userId |
| Sort key | interviewId |
| Billing mode | On-demand |

#### Data checks after running the app

* After CV upload, an item must exist in CVs.
* After CV analysis, the CVs item should include skills, summary, status.
* After creating an interview, an item must exist in Interviews.
* After answering questions, Interviews should include answers, attempts, score, or finalScore.

#### Lambda environment variables

```text
CVS_TABLE=CVs
INTERVIEWS_TABLE=Interviews
```
