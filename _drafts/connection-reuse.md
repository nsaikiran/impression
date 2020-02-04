---
layout: post
title:  "Connection reusing"
description: "How to deal with connections?"
categories: ["cs"]
type: "Scribe"
author: "Sai Kiran"
---


Establishing a connection is costly and connections are re-usable.

Re-using connections improves save us lot of performance.
How many connections to the server can be opened? Is the important point to achieve the best 
performance.

Connection pooling:
- [HikariCP - About pool sizing](https://github.com/brettwooldridge/HikariCP/wiki/About-Pool-Sizing)
- [Real-World Performance - 13 - Large Dynamic Connection Pools - Part 1](https://www.youtube.com/watch?v=Oo-tBpVewP4)
- [Real-World Performance - 14 - Large Dynamic Connection Pools - Part 2](https://www.youtube.com/watch?v=XzN8Rp6glEo)
- old video [OLTP Performance - Concurrent Mid-Tier Connections](https://www.youtube.com/watch?v=xNDnVOCdvQ0)

Even from HTTP/1.1 connections to the webservers are reused by using keep-alive header

How nginx handles many connections simultaneously.
- [How Does NGINX Work?](https://www.nginx.com/blog/inside-nginx-how-we-designed-for-performance-scale/#process-model) read the comments. 
They are very informative.
- [Socket sharding nginx](https://www.nginx.com/blog/socket-sharding-nginx-release-1-9-1/)


