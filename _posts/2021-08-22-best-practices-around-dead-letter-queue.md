---
layout: post
title: Best practices around dead letter queue
subtitle: Industry proved best practices for handling messages in dead letter queue.
categories: AWS
tags: [BestPractices, AWS, SQS, DLQ]
comments: true
---

- DLQ Retention should be set to maximum 14 days.
- To give messages a better chance to be processed before sending them to the dead-letter queue, set the maxReceiveCount on the source queue's re-drive policy to at least 5.
- Re-drive script should be at handy place with a good documentation on Runbook.
- A combination of Alarms as per recommendation
  - Low Severity: > 0 message
  - High Severity: > [high impact threshold] messages
  - Medium Severity: [DLQ.Retention - DLQ.ApproximateAgeOfOldestMessage] < 5-7 days
