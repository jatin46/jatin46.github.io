---
layout: post
title: Error handling in AWS Lambda when invoking through SQS
categories: AWS
tags: [Lambda, SQS, BestPractices]
comments: true
---

If a message fails to be processed multiple times, Amazon SQS can send it to a dead-letter queue. To send messages to a second queue after a number of receives, configure a dead-letter queue on your source queue.
To give messages a better chance to be processed before sending them to the dead-letter queue, set the maxReceiveCount on the source queue's redrive policy to at least 5.

> Make sure that you configure the dead-letter queue on the source queue, not on the Lambda function. The dead-letter queue that you configure on a function is used for the function's asynchronous invocation queue, not for event source queues.
