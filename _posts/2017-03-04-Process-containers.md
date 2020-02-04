---
layout: post
title:  "Process Containers"
description: "Understanding container technology"
categories: ["tech"]
tags: ["container", "docker", "kubernetes"]
author: "Sai Kiran"
---

*This is not a thorough discussion about **process containers**. 
This post is an introduction and a bag of resources.*

### [Why][What are containers and how did they come about?] containers?

We have been using virtualization technology in developing and deploying the software systems. 
Now, why are we using containers? What are the advantages of using containers?
Here are some advantages of containerization of applications.
- Container images can be easily exchanged
- Less performance overhead
- Lower the cost
- Security
- Ease in deploying [microservices][MicroServices  MartinFowler] architecture. 

[Process Containers][Linux Containers: Why They’re in Your Future and What Has to Happen First]
is a way to run many _isolated applications_ on a _single host_.
When your application has many processes/services that needs to co-ordinate with each other, 
then you can containerize each of these processes. This idea has many benefits.
For example, a web server and a database server co-ordinate each other to make up your web application.
You can create a container for web server and one for database server and connect them.
[This ensure that if attackers compromised a container, they will have only *that* container, 
as they are **blind** to outside of the container.][Containers rated more secure than conventional apps]

### [What][What are containers and how did they come about?] are containers?

[Containers are awesome Kernel Parlor Tricks][Kubernetes in 5 minutes].

Containerization is operating-system-level-virtualization or simply &mdash; isolation.
When we take a set of processes and isolate them from  rest of the processes, 
and restrict them to use a specified amount of system resources (CPU, memory, disk etc.), 
then we call them a container. Containers are possible because of the 
[Control Groups][Kernel ControlGroups] (For managing and monitoring resource usage) and 
[Namespaces][Kernel NameSpaces] (To isolate processes) that are part of Linux Kernel.

Container is a *set* of isolated processes &mdash; means processes inside the container 
will not be aware of anything outside the container. You isolate a group of processes. 
And restrict that group to use a specified amount of resources.
Then, any of the processes can *overeat* the specified amount of resources &mdash;
there by making the other processes in that set to starve or to *terminate*. 
To avoid that docker recommends and enforces [*one* process per container][Cgroups, namespaces, and beyond: what are containers made from?].

You might have played with containers, may be with the help from any of the technologies &mdash; like docker.
But, [you can create a container yourself][Cgroups, namespaces, and beyond: what are containers made from?].
For more insights of containers, and comparison of virtualization and containers, refer [Architecting Containers\*][Architecting Containers].


### Docker
When I was trying the docker technology, 
It made to think: Why do we need a base image,
if the process in the container is using the same kernel of the host? 
The answer is in the question itself. 
Containers will only use the `kernel` of the host &mdash; not the `userland` software. 
[Base image contain the userland of the distribution on which we want our application
to run.][Why Understanding User Space vs. Kernel Space Matters]
Different linux distributions have different `userland` software. 

We have another technology &mdash; kubernetes. [We need kubernetes because containers can't think outside the kernel][Kubernetes in 5 minutes]


### More Resources
- [Architecting Containers\*][Architecting Containers]
- [Make Containers Contain and Work for You][Make Containers Contain and Work for You] discusses security aspect of containers &mdash;  especially in Docker.
- [The Application Apartment Complex: Red Hat Enterprise Linux & Linux Containers][The Application Apartment Complex: Red Hat Enterprise Linux & Linux Containers]
- [What are containers and why do you need them?](http://www.cio.com/article/2924995/enterprise-software/what-are-containers-and-why-do-you-need-them.html)
- [Operating System Containers vs. Application Containers](https://blog.risingstack.com/operating-system-containers-vs-application-containers/)

[Kubernetes in 5 minutes]: https://www.youtube.com/watch?list=PL4jrq6cG7S45weX1mb-o7H4bRG3YHrCyS&v=N6r-9ZzFgzw
[Linux Containers: Why They’re in Your Future and What Has to Happen First]: https://www.cisco.com/c/dam/en/us/solutions/collateral/data-center-virtualization/openstack-at-cisco/linux-containers-white-paper-cisco-red-hat.pdf
[What are containers and how did they come about?]:http://bitmason.blogspot.in/2013/09/what-are-containers-anyway.html
[Make Containers Contain and Work for You]: http://containerjournal.com/2016/09/23/make-containers-contain-work/
[Architecting Containers]: http://rhelblog.redhat.com/tag/architecting-containers/
[The Application Apartment Complex: Red Hat Enterprise Linux & Linux Containers]: http://rhelblog.redhat.com/2014/03/31/containers/
[MicroServices  MartinFowler]: https://www.youtube.com/watch?v=wgdBVIX9ifA&t=397s
[Kernel NameSpaces]: https://lwn.net/Articles/531114/
[Kernel ControlGroups]: https://lwn.net/Articles/621006/
[Cgroups, namespaces, and beyond: what are containers made from?]: https://www.youtube.com/watch?v=sK5i-N34im8
[Containers rated more secure than conventional apps]: https://www.theregister.co.uk/2016/07/15/containers_rated_more_secure_than_conventional_apps/
[Why Understanding User Space vs. Kernel Space Matters]: https://rhelblog.redhat.com/2015/07/29/architecting-containers-part-1-user-space-vs-kernel-space/