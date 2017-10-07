---
layout: post
title:  "Behind the magic curtains: Spring Boot"
categories: ["cs"]
author: "Sai Kiran"
---

When we enjoy the benefits of a system, 
without the knowledge of *how* it does, 
we will naturally have desire to explore. 
*Behind the magic curtains* is a series of writings about such systems. 
This post is the first of this series. 
Below described is my experience while trying to understand Spring Framework, projects built on Spring Framework and one of those projects: Spring Boot.

 
After realizing that the Spring ecosystem is very big and my experience with it considerably low. 
I wanted to try to understand at least basic idea on how Spring components are organized and used &mdash; at high level.

---

## Spring Framework


Ask these questions to yourself and you'll be right on track to understand:

- Why Spring Framework?
- What is Spring Framework and What are its components?
- What is the minimal Spring Framework I can use?
- What are the projects built on Spring Framework?

### Why Spring Framework?

> Whenever we observe boilerplate code, 
> we extract that out and invoke from where ever we want that functionality. 
> If that piece of code is boilerplate code for most of the developers, then it will be a part of library or framework.
>And you need to be through with the *[guidelines][GuidelinesPOST]* 
> for an effective and proper use of a framework or a library.

Spring Framework required because it provides lot of boilerplate code. 
Going through below videos will help in figuring out *what* boilerplate code it provies. 
- [Getting Started with Spring and SpringSource Tool Suite (STS) Part 1][SpringVideo1], 
- [Getting Started with Spring and SpringSource Tool Suite (STS) Part 2][SpringVideo2]

All other features of the framework are described in a lengthy [reference manual][Spring Link 2]. But that'll be very useful.

### What is Spring Framework and What are its components?
[Spring Framework project][Spring Framework Project] is foundation for all other Spring projects.
[Overview of the Spring Framework][Framework Modules] was very helpful to uncover some parts of the gray area.
There the anatomy of the framework is described. 

Spring Framework contains modules such as `spring-core`, `spring-beans`, `spring-context` and many others.
To know more related to the modules, check [Source Code of Spring Framework][Source Code of Spring Framework]. 
Have a glance at build scripts of those modules, to figure out how those modules make up framework.

### What is the minimal Spring Framework I can use?
The recommended *minimal* Spring Framework to use is `spring-context`. 
Find out features of and how-to-use the framework [here][Spring Framework Project].

### What are the projects built on Spring Framework?
You can find them in [Spring Projects Page][Spring Projects].


----

Foundational concepts of Spring 
http://springtutorials.com/spring-tutorial-1/ It has good concepts.

----

### Bookmarks
- [Spring Reference][Spring Link 1]

---

## SpringBoot
It is one of the Spring projects built on Spring Framework. 
Find more here at [Spring Boot project page][Spring Boot project page].

We generally need to configure the framework with one of 
these configuration methods available &mdash; xml, java configuration and annotation based.


Now, SpringBoot will (conditionally)configure our application context by *convention* unless we come up with 
our own configuration. 
Allowing us to get started with the application quickly. 
It will check your classpath for what module/project you want to use 
in your application and configures it for you. 

It also provides many features other than configuring like &mdash; embedded servlet container &mdash; to create standalone application. 
The way it works is so cool and easy to understand. 
It uses Java based configuration to configure the framework. 

[Demystifying SpringBoot Magic][Demystifying SpringBoot Magic] and [Zero Effort Spring][Zero Effort Spring] will 
demonstrate how SpringBoot does all the magic. 


### Bookmarks
- [Spring Boot Reference][Springboot Link 1]

### Videos
- [Demystifying SpringBoot Magic][Demystifying SpringBoot Magic].
- [Zero Effort Spring][Zero Effort Spring].

---

## Annotations
Java annotations also seemed interesting for me after doing all this Spring stuff. 
Just keep an annotation on an element and that's it, you will see that element being affected as promised by the annotation. 

I was curious to know how those annotations work on our piece of code. 
And the concept seemed a bit weird and unusual. 
Providing our own annotation is not so simple. 
But annotations are handy.

Anyway, [Annotation Processing][Annotation Processing 101] gives some insights in "processing" annotations.

In python we have similar language construct called `decorator`. 

### Bookmarks
- [How do annotations work internally][How do annotations work internally]



[Annotation Processing 101]: http://hannesdorfmann.com/annotation-processing/annotationprocessing101
[How do annotations work internally]: https://stackoverflow.com/questions/18189980/how-do-annotations-work-internally

[Spring Link 1]: http://docs.spring.io/spring/docs/current/spring-framework-reference/htmlsingle/
[Spring Link 2]: https://docs.spring.io/spring/docs/4.3.9.RELEASE/spring-framework-reference/htmlsingle/
[SpringOverView]: https://docs.spring.io/spring/docs/current/spring-framework-reference/html/overview.html
[Framework Modules]: https://docs.spring.io/spring/docs/4.3.9.RELEASE/spring-framework-reference/htmlsingle/#overview-modules
[Spring and Spring Framework]: https://docs.spring.io/spring/docs/5.0.x/spring-framework-reference/overview.html#what-we-mean-by-spring
[Source Code of Spring Framework]: https://github.com/spring-projects/spring-framework
[Spring Framework Project]: http://projects.spring.io/spring-framework/
[Spring Projects]: https://spring.io/projects
[SpringVideo1]: https://www.youtube.com/watch?v=kSITVsOUvLU
[SpringVideo2]: https://www.youtube.com/watch?v=u3axrmN-wrE
[Springboot Link 1]: http://docs.spring.io/spring-boot/docs/current/reference/htmlsingle/
[Spring Boot project page]: http://projects.spring.io/spring-boot/
[Demystifying SpringBoot Magic]: https://spring.io/blog/2016/12/14/spring-tips-demystifying-bootiful-magic
[Zero Effort Spring]: https://www.youtube.com/watch?v=cTPAKMIm_pM&list=PLgGXSWYM2FpOa_FTla-x5Wd10dpmgrRC4

------
[GuidelinesPOST]: http://saikiran.blog/cs/2017/04/15/the-guidelines-and-different-varieties-of-perceiving.html