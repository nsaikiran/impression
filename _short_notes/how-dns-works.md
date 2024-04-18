---
layout: post
title:  "How DNS works"
description: "How DNS works"
categories: ["release-technique"]
date: 18-04-2023
author: "Sai Kiran"
---

While understanding [how the DNS works and how it is distributed globally and scaled well](https://www.youtube.com/watch?v=g_gKI2HCElk), I came across one important networking concept. That is anycast in networks. There are some DNS root servers in the world, each root server advertises to have more than one IP address. Each root server has physical server instances distributed across the globe. The request will be routed to geographically nearest physical server. But how that is possible is yet to understand, it is said that BGP helps doing this. 

## My understanding
Like routers maintaining more than one route to reach an IP addresses, in anycast, the routers will have more than one path to reach, but infact those paths are to different physical instance. Understand this more.
Looks like CDNs also uses similar approach to serve static content from the nearest edge server.

[Long time back google has implemented high available load balancers using this technique](https://www.youtube.com/watch?v=WjT253DBlXk).