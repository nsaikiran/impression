---
layout: post
title:  "Scaling the application"
description: "How to scale applications for increased users, load with cost effectiveness"
categories: ["system-design"]
date: 15-03-2024
author: "Sai Kiran"
---

Software applications should be able to serve increased users and load with reasonable cost. The goal of the businesses have been to build highly available software with resonable opertaing cost. 

## Reading material
(This is not an exhaustive list of resources, and not in any particular order. The goal is first understand various concepts, various usecases in which these concepts can be applied and implementations of these concepts. For example: what are the load balancers, reverse proxies, web servers, caches, databases that can be used. And also, it is important to know various characteristics of our systems such as how many requests/users one node of our system can handle so that we take an informed decision)
1. [The System Design Primer](https://github.com/donnemartin/system-design-primer/blob/master/README.md) has described the general concepts that are required for scaling software systems. This guide cites very informative articles or blog posts from various industry experts.
2. [Scaling on AWS for the First 10 Million Users](https://www.youtube.com/watch?v=LbiPMKDNdvY) and [its slides](https://www.slideshare.net/AmazonWebServices/scaling-on-aws-for-the-first-10-million-users-at-websummit-dublin-41845658?from_search=9). 
   - Every year, AWS team have a presentation that talks about _Scaling Up to Your First 10 Million Users with AWS offerings_, the link I've mentioned here is the oldest I could find (I think this is from 2013), but if there is older one prefer that one, because the latest talks mentions latest AWS offerings which are very abstract. 
   - The goal here is to understand the concepts.
   - Some of the previous events are [2014 | Scaling Up to Your First 10 Million Users](https://www.youtube.com/watch?v=ccojvcQq858), [Deep Dive: Scaling Up to Your First 10 Million Users / 2015](https://www.youtube.com/watch?v=KulMgJnMLsw), find the respective slides from [slideshare](https://www.slideshare.net/search?utf8=%E2%9C%93&searchfrom=header&q=+Scaling+on+AWS+for+the+First+10+Million+Users+). Compare the slides to learn differences.
3. [It's all a numbers game](https://www.youtube.com/watch?v=1KRYH75wgy4) Try to get the numbers for the system by having clear understanding, numbers don't lie and they'll give a chance to unambiguous and informed scaling decision.

Go through these and list down concepts and describe those concepts.
