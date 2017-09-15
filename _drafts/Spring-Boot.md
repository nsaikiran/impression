---
layout: post
title:  "Behind the magic curtains: Spring Boot"
categories: ["cs"]
author: "Sai Kiran"
---

Understanding Spring Framework.

*Aim of this post is not to give specific details about Spring and its eco system, rather to give a generic idea of Spring **framework**, its extensibility.*


Understanding Spring Framework. not any specific spring project that uses framework/core.
Focus on core. How it is extensible? How other projects like security/data access/mvc are connected to spring-core?


# Annotations
Annotations have been very handy in influence the definitions. Now we use them everywhere. 
Especially in configuring Spring. 
I was curious to know how those annotations work on our piece of code. I came to know that this is a weird and unusual concept.


Anyway, [Annotation Processing][Annotation Processing 101] gives some insights in "processing" annotations.
## Bookmarks
- [How do annotations work internally][How do annotations work internally]

# Inversion of Control
//TODO: Talk about frameworks. How inversion of control works.


# Spring
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
[Springboot Link 1]: http://docs.spring.io/spring-boot/docs/current/reference/htmlsingle/
[Demystifying SpringBoot Magic]: https://spring.io/blog/2016/12/14/spring-tips-demystifying-bootiful-magic
[Zero Effort Spring]: https://www.youtube.com/watch?v=cTPAKMIm_pM&list=PLgGXSWYM2FpOa_FTla-x5Wd10dpmgrRC4