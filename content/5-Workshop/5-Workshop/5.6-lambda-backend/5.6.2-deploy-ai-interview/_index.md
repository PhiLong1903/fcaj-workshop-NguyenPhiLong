---
title: "Deploy analyze_cv, create_interview, submit_answer"
date: 2026-07-21
weight: 2
chapter: false
pre: " <b> 5.6.2. </b> "
---

#### Deploy `analyze_cv`

1. Create Lambda `analyze_cv`.
2. Copy code from:

```text
backend/analyze_cv/lambda_function.py
```
![Cognito flow](/fcj-workshop-huydat/images/5-Workshop/service-image/1.562.png)

3. Add environment variables:

![Cognito flow](/fcj-workshop-huydat/images/5-Workshop/service-image/2.562.png)

4. Add PDF extraction layer if needed:

```text
backend/analyze_cv/analyze_cv_pypdf_layer.zip
```

#### Deploy `create_interview`

```text
backend/create_interview/lambda_function.py
```

![Cognito flow](/fcj-workshop-huydat/images/5-Workshop/service-image/3.562.png)

Environment variables:
![Cognito flow](/fcj-workshop-huydat/images/5-Workshop/service-image/4.562.png)


#### Deploy `submit_answer`

```text
backend/submit_answer/lambda_function.py
```
![Cognito flow](/fcj-workshop-huydat/images/5-Workshop/service-image/5.562.png)
Environment variables:

![Cognito flow](/fcj-workshop-huydat/images/5-Workshop/service-image/6.562.png)

These Lambdas need `bedrock:InvokeModel` and matching DynamoDB read/write permissions.
