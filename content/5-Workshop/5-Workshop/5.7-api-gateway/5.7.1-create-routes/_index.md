---
title: "Create routes and Lambda integrations"
date: 2026-07-21
weight: 1
chapter: false
pre: " <b> 5.7.1. </b> "
---

#### Create API

1. Open **Amazon API Gateway**.
![Cognito flow](/fcj-workshop-huydat/images/5-Workshop/service-image/1.571.png)
2. Choose **Create API**.
![Cognito flow](/fcj-workshop-huydat/images/5-Workshop/service-image/1.571.png)
3. Choose **HTTP API**.
![Cognito flow](/fcj-workshop-huydat/images/5-Workshop/service-image/2.671.png)
4. Create integrations to each Lambda.
5. Create routes from the table in section `5.7`.
6. Create a stage, for example:

```text
default
```

7. Copy the invoke URL for the frontend.

#### Example deployed endpoint

```text
https://<api-id>.execute-api.ap-southeast-1.amazonaws.com/default/upload_cv
```

#### Route checks

* Each route points to the correct Lambda.
* Lambda permission allows API Gateway to invoke the function.
* Stage is deployed or auto deploy is enabled.
