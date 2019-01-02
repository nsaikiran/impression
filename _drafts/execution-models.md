---
layout: post
title:  "Execution models"
description: "Various execution models"
categories: ["tech", "cs"]
tags: ["execution-models"]
author: "Sai Kiran"
---


>> The goal is to explain learning execution model means going to bigger picture. (Merge bigger picture post with this and make them one?.). Bigger picture drives. It convinces details of specific instance. Bigger picture is always simple.


Motivation: Execution models will help better usage of tools.
Various types of execution models like event-driven(nginx?), process based(apache?). Gather other generic types of models and produce some examples for each. Learning those generic concepts which will live logner will be a good investement. [Stop Learning Frameworks](https://sizovs.net/2018/12/17/stop-learning-frameworks/) tries to explain that.

Three major execution models are mentioned and explained [here](http://www.nettreo.com/2016/07/07/understanding-programming-language-execution-models/)

Execution model of [Python web](https://blog.xoxzo.com/2012/05/02/php-execution-model-vs-python-web/)
[Java] (https://docs.oracle.com/javase/specs/jls/se7/html/jls-12.html)
[Apache vs Nginx](https://foxutech.com/apache-vs-nginx-architecture/)
# Languages
## (TODO: Event loop model of JS )JavaScript
JavaScript execution model is better explained in [Concurrency model and Event Loop][Concurrency model and Event Loop].
Because it runs on single thread it may needs to run instructions [asynchronously][asynchronous]; otherwise you'll end up in 
non-responsive runtime. 
If you want to understand event loop properly 
then you would never want to miss this awesome presentation named *[In the Loop][In the Loop]*. 
You'll enjoy that presentation.

## TODO: Execution model of Interpreted langs. and compiled langs.
## Ex: python and C

# Webframeworks
[Web frameworks - an overview](https://www.ionos.com/digitalguide/websites/web-development/web-frameworks-an-overview/) explains bring vocabular related to webframeworks.

## TODO: WSGI. Communication between HTTP server and Django
## Django

## TODO: Communication between spring-web and Jetty.
*Servlet* and *Servlet Container* spec.
[Servlet Spec][Servlet Spec]


# Configurability
> Sometimes we just need to understand how a system works and should be able to configure it to match our needs.

## Drupal (Content Management System)







[Concurrency model and Event Loop]: https://developer.mozilla.org/en-US/docs/Web/JavaScript/EventLoop
[In the Loop]: https://www.youtube.com/watch?v=cCOL7MC4Pl0
[How JavaScript works: Event loop and the rise of Async programming + 5 ways to better coding with async/await]: https://blog.sessionstack.com/how-javascript-works-event-loop-and-the-rise-of-async-programming-5-ways-to-better-coding-with-2f077c4438b5
[PHP execution model vs Python web]: https://blog.xoxzo.com/2012/05/02/php-execution-model-vs-python-web/

[asynchronous]: https://www.webopedia.com/TERM/A/asynchronous.html

[Servlet Spec]: https://jcp.org/aboutJava/communityprocess/final/jsr340/index.html
