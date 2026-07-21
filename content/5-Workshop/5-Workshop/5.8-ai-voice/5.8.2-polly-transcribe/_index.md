---
title: "Configure Polly and Transcribe"
date: 2026-07-21
weight: 2
chapter: false
pre: " <b> 5.8.2. </b> "
---

#### Amazon Polly

Polly is used for English questions:

```text
POLLY_VOICE_ID=Joanna
POLLY_ENGINE=standard
```

`polly_speech` creates an MP3 file, stores it in S3, and returns a presigned URL for the frontend to play.

#### Amazon Transcribe

Transcribe is used for microphone input:

```text
TRANSCRIBE_LANGUAGE_CODE=en-US
```

If the user selects Vietnamese, frontend/backend should send:

```text
vi-VN
```

#### Vietnamese note

Amazon Transcribe supports Vietnamese speech recognition with `vi-VN`. For Vietnamese question speech, Amazon Polly does not provide a common Vietnamese voice like English voices, so browser speech synthesis or another Vietnamese TTS provider can be used.

#### Microphone checks

* The deployed frontend must use HTTPS.
* Audio must be fully uploaded to S3.
* Transcribe job should be polled until `COMPLETED`.
* If transcript is too short, check recording duration, silence at the start, and `languageCode`.
