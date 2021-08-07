---
layout: post
title: EMR best practice while writing output to S3
subtitle: Learned the hard way
categories: AWS
tags: [EMR, Spark, S3, BestPractices]
comments: true
---

We should always use Spark's overwrite mode while writing to s3 unless your use case does not support it.
This is because S3 is a distributed system and though rare but it can throw an internal 500 exception. In this case, Spark will try to retry the failed task but if we don't use overwrite mode then the task might again fail with FileAlreadyExists error since some files might already have been written to S3.
