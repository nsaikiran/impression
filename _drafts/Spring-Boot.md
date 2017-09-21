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


You probably know the difference between library and framework. Using libraries won't be intriguing or irritating but using a framework does. 
Because guidelines that one needs to follow to use framework or more when compared to library. 

> TODO picture of skeleton > framework, full picture for application

# Inversion of Control
//TODO: Talk about frameworks. How inversion of control works.


# Annotations
Annotations have been very handy in influence the definitions. Now we use them everywhere. 
Especially in configuring Spring. 
I was curious to know how those annotations work on our piece of code. 
I came to know that this is a weird and unusual concept.

Anyway, [Annotation Processing][Annotation Processing 101] gives some insights in "processing" annotations.
## Bookmarks
- [How do annotations work internally][How do annotations work internally]


# Spring Framework


When we are developing applications with using Spring Framework. Lot of questions arise. 
When you feel the magic, naturally you'll want to know &mdash; How things are happening under the hood.

I've the same feeling. So, started to understand Spring Framework.

I found the [Overview of Spring Framework][SpringOverView] very helpful to at least uncover some part of the gray area.
There described the anatomy of framework. 

You might also want to go through the complete reference manual of framework except that it is lenghty. But that'll be very useful.

Some of the questions I tried to chase are answered there are:
- What is the minimal spring you can use?
- How the *minimal spring* extended with other essential modules ?
- What are all the modules of the framework?


And as we were mentioning *what* boilerplate code is provided by the framework ?
[Getting Started with Spring and SpringSource Tool Suite (STS) Part 1][SpringVideo1], 
[Getting Started with Spring and SpringSource Tool Suite (STS) Part 2][SpringVideo2]
has good explanation of core features of Spring Framework. All other features of the framework are described in reference manual.



Understanding Spring Framework. not any specific spring project that uses framework/core.
Focus on core. How it is extensible? How other projects like security/data access/mvc are connected to spring-core?



Foundational concepts of Spring 
http://springtutorials.com/spring-tutorial-1/ It has good concepts.


## Bookmarks
- [Spring Reference][Spring Link 1]

# SpringBoot
They say it is a opinionated configuration of Spring. You can change that by customizing.
## Bookmarks
- [Spring Boot Reference][Springboot Link 1]

### Videos
- [Demystifying SpringBoot Magic][Demystifying SpringBoot Magic].
- [Zero Effort Spring][Zero Effort Spring].


This post will be as much generic as Spring/Spring Boot it self ;). It doesn't include all specific details.



I hope I've tried to uncover at least few of the magic curtains if not some.


[Annotation Processing 101]: http://hannesdorfmann.com/annotation-processing/annotationprocessing101
[How do annotations work internally]: https://stackoverflow.com/questions/18189980/how-do-annotations-work-internally

[Spring Link 1]: http://docs.spring.io/spring/docs/current/spring-framework-reference/htmlsingle/
[SpringOverView]: https://docs.spring.io/spring/docs/current/spring-framework-reference/html/overview.html
[SpringVideo1]: https://www.youtube.com/watch?v=kSITVsOUvLU
[SpringVideo2]: https://www.youtube.com/watch?v=u3axrmN-wrE
[Springboot Link 1]: http://docs.spring.io/spring-boot/docs/current/reference/htmlsingle/
[Demystifying SpringBoot Magic]: https://spring.io/blog/2016/12/14/spring-tips-demystifying-bootiful-magic
[Zero Effort Spring]: https://www.youtube.com/watch?v=cTPAKMIm_pM&list=PLgGXSWYM2FpOa_FTla-x5Wd10dpmgrRC4