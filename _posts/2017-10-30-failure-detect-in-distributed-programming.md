---
layout: post
title: 分布式编程中的故障探测
categories: [distributed-programming]
description: distributed-programming
keywords: distributed-programming
---

在分布式系统中，自然状态下是一个异步网络，因此故障探测很难做到同时具有`完整性`和`准确性`。
因此我们可以其大致将这两个分为强弱之分：

* 强完整性：每一个宕机的进程最终都能被每个正常的进程发现；
* 弱完整性：每一个宕机的继承最终只能被一些正常的进程发现；
* 强准确性：正常的进程不会被归为宕机状态；
* 弱准确性：正常的进程中的一部分从来不会被归为宕机状态；

完整性相对来说比较好实现，准确性相对来说比较难实现，因为在异步网络中，很难分辨到底是真的
宕机了还是网络延时了。

#### Refer
* [Distributed systems - replication](http://book.mixu.net/distsys/replication.html)
