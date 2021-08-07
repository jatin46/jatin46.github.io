---
layout: post
title: Don't do this with your AWS account
subtitle: Best practices while setting up new account
categories: AWS
tags: [AWS, BestPractices]
comments: true
---

If you're a developer and planning to build a service in the cloud then don't merge it with your existing account. The common mistake that most teams or developers make is to run multiple services in a single account which later becomes a single point of failure. Moreover, if a hacker or unauthorised person gets access to your account then it can tempered all the resources in one go.
You should use a single account for one service and if your service is spread across multiple regions then you should even create different accounts for different regions. This will also give you extra benefits of free-tier which comes with the account.

