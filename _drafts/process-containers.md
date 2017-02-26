---
layout: post
title:  "Process Containers"
categories: ["tech"]
author: "Sai Kiran"
---

[What are containers and how did they come about?][What are containers and how did they come about?]
Was really helpful in understaing containers.

This is not a thorough discussion about *process containers*.

These are the words &mdash; with many other, are ubiquitous:`Docker` and `Containers`.

This discussion is about the ideas of isolated process execution or process containers.

[Linux Containers][Linux Containers] is a way to run many _isolated applications_ on a _single host_.

Containers are made of linux kernel core features &mdash namespaces, and cGroups.

Technically they container is a set of processes restricted to use limited amount of computer resources (cGroups).

Containers are widely used in microservices.



**[MAIN TODO]** How to create a containers.

I was actually trying to understand the mystery behind 
the isolated process execution. 
Accounting of resource utilization and allocating resources 
for processes and securing the host computer by restricting 
the processes. Because they are _native procesess_,
we can have good amount of flexibility over the processes.

[Containers are awesome Kernel Parlor Tricks][Kubernetes in 5 minutes].

[We need kubernetes because containers can't think outside the kernel][Kubernetes in 5 minutes]

### What is operating system level virtualization.

### What happens before a container starts.

### References
Read [this](http://www.cio.com/article/2924995/enterprise-software/what-are-containers-and-why-do-you-need-them.html). Really good and talks about why application containers / container technology.



[Kubernetes in 5 minutes]: https://www.youtube.com/watch?list=PL4jrq6cG7S45weX1mb-o7H4bRG3YHrCyS&v=N6r-9ZzFgzw
[Linux Containers]: https://www.cisco.com/c/dam/en/us/solutions/collateral/data-center-virtualization/openstack-at-cisco/linux-containers-white-paper-cisco-red-hat.pdf
[What are containers and how did they come about?]:http://bitmason.blogspot.in/2013/09/what-are-containers-anyway.html
