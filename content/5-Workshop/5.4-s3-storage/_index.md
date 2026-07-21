---
title: "Deploy Amazon S3"
date: 2026-07-21
weight: 4
chapter: false
pre: " <b> 5.4. </b> "
---

#### Goal

Amazon S3 stores files that should not be stored directly in the database: CVs, question audio, answer audio, and transcripts.

![Cognito flow](/fcaj-workshop-NguyenPhiLong/images/service-image/5_4.png)

#### Object structure

```text
cv/{userId}/{cvId}.{extension}
voice/questions/{userId}/{interviewId}/{questionIndex}.mp3
voice/answers/{userId}/{interviewId}/{questionIndex}.webm
voice/transcripts/{jobName}.json
```

The bucket is used by upload_cv, analyze_cv, polly_speech, transcribe_audio, and several admin features.
