---
layout: post
title: Capacity delusion of DynamoDB throughput
subtitle: Cause of throttling on DynamoDB table.
categories: AWS
tags: [AWS, DynamoDB, BestPractices]
comments: true
---

One day we started seeing throttling on the DynamoDB table because of the spike in traffic. To mitigate the issue we increased the provisioned throughput without knowing the long-lasting impact of excessive scaling. The extra throughput which we provide caused DynamoDB to increase the number of partitions. Once the traffic gets normal we bring back the throughput to previous levels but now we noticed that some requests are still throttling even when we have not exceeded the provisioned throughput on the table. This happens because there are fewer read and write throughput units per partition than before due to the increased no. of partitions. The no. of partitions in a DynamoDB table goes up in response to increased load or storage size, but it never comes back down. Now, we’ve to pay for higher throughput even though we are not consuming the extra throughput till we migrate to a new table. 

