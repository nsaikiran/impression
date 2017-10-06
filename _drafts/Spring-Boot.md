---
layout: post
title:  "Behind the magic curtains: Spring Boot"
categories: ["cs"]
author: "Sai Kiran"
---

Understanding Spring Framework.

*Aim of this post is not to give specific details about Spring and its eco system, rather to give a generic idea of Spring **framework**, its extensibility.*

Boilerplate code!, whenever we observe we'll try not to copy the same code in several places. 
We extract that out and invoke from where ever we want that functionality. 

If that piece of code is boilerplate code for most of the developers, then it will be a part of library or framework.


You probably know the difference between library and framework. 
And you need to be through with the *[guidelines][GuidelinesPOST]* needs to be followed for an effective 
and proper use.

> TODO picture of skeleton > framework, full picture for application

# Inversion of Control
//TODO: Talk about frameworks. How inversion of control works.


## Annotations
Annotations have been very handy in influence the definitions. Now we use them everywhere. 
Especially in configuring Spring. 
I was curious to know how those annotations work on our piece of code. 
I came to know that this is a weird and unusual concept.

In python we have similar language construct called `decorator`. Where you can influence the wrapped (annotated) function.

Anyway, [Annotation Processing][Annotation Processing 101] gives some insights in "processing" annotations.
### Bookmarks
- [How do annotations work internally][How do annotations work internally]


## Spring Framework

When we are developing applications with using Spring Framework. 
Lot of questions arise. 
When you feel the magic, naturally you'll want to know &mdash; How things are happening under the hood.

I've the same feeling. So, started to understand Spring Framework.

The latest release of Spring Framework came with the updated reference document which described what they mean by [*'Spring and Spring Framework'*][Spring and Spring Framework].
So, lets talk about Spring *Framework*.

You might also want to go through the complete reference manual of framework except that it is lenghty. But that'll be very useful.

Ask these questions to yourself and you'll be right on track to understand:

- Why Spring Framework?
- What is Spring Framework and What are its components?
- What is the minimal Spring Framework I can use?
- What are the projects built on Spring Framework?

### Why Spring Framework?
And as we were mentioning *what* boilerplate code is provided by the framework ?
[Getting Started with Spring and SpringSource Tool Suite (STS) Part 1][SpringVideo1], 
[Getting Started with Spring and SpringSource Tool Suite (STS) Part 2][SpringVideo2]
has good explanation of core features of Spring Framework. All other features of the framework are described in reference manual.

### What is Spring Framework and What are its components?
Spring Framework project is foundation for all other Spring projects. 
You can check the list of all projects at [Spring Projects][Spring Projects]. 
Each project contains several modules. 
For example Spring Framework contains `spring-core`, `spring-beans`, `spring-context` and many others.

I found [Overview of the Spring Framework][Framework Modules] very helpful to at least uncover some part of the gray area.
There the anatomy of the framework is described. 
 
To know more related to the modules, check [Source Code of Spring Framework][Source Code of Spring Framework].  
Also you might want to check the build script of each module to figure out dependency tree of those modules.

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



[Annotation Processing 101]: http://hannesdorfmann.com/annotation-processing/annotationprocessing101
[How do annotations work internally]: https://stackoverflow.com/questions/18189980/how-do-annotations-work-internally

[Spring Link 1]: http://docs.spring.io/spring/docs/current/spring-framework-reference/htmlsingle/
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