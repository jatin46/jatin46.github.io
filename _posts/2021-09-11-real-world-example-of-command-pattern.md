---
layout: post
title: Real-World Example of Command Design Pattern
categories: DesignPattern
tags: [Java, Command Pattern]
comments: true
---

The command design pattern is my most favourite design pattern which I’ve used a lot. Let me share with you one of the instances where I used this pattern.
I got the below use case:
- Read the data from S3 in an EMR.
- Load that data into the Redshift temporary table.
- Run a join command between that temporary table and another Redshift table.
- Unload the resulting data back to an EMR.
- Write that data to an S3 bucket as an output.

As evident from the above use case, I had to pass down the result to a set of commands which needs to be executed in a serialized fashion and that makes it a perfect use case of Command Pattern. The biggest advantage of this pattern is that I can add or remove any command without affecting the rest of the code.
