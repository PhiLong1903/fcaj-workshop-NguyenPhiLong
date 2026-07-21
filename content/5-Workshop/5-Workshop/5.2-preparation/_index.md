---
title: "Environment preparation"
date: 2026-07-21
weight: 2
chapter: false
pre: " <b> 5.2. </b> "
---

#### Goal

Prepare the AWS account, Region, budget, source code, and configuration values before deploying each service.


#### Preparation checklist

| Item | Expected result |
| --- | --- |
| AWS account | Permission to create Cognito, S3, DynamoDB, Lambda, API Gateway, Bedrock, Polly, Transcribe, Amplify. |
| Region | Use one consistent Region, for example ap-southeast-1. |
| Budget | Cost alerts to control Bedrock/Transcribe/Amplify usage. |
| Source code | Repository contains frontend/ and backend/. |
| API test tool | Postman or curl for API Gateway testing. |
| Browser | Chrome/Edge for Cognito, microphone, and responsive UI testing. |

#### Values to record

* AWS Account ID
* Region
* S3 bucket name
* DynamoDB table names
* Lambda function names
* API Gateway invoke URL
* Cognito User Pool ID
* Cognito App Client ID
* Amplify domain
