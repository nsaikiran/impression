---
layout: post
title:  "Execution models"
description: "Various execution models"
categories: ["tech", "cs"]
tags: ["execution-models"]
author: "Sai Kiran"
---


#TODO: Event loop model of JS 
## JavaScript
JavaScript execution model is better explained in [Concurrency model and Event Loop][Concurrency model and Event Loop].
Because it runs on single thread it may needs to run instructions [asynchronously][asynchronous]; otherwise you'll end up in 
non-responsive runtime. 
If you want to understand event loop properly 
then you would never want to miss this awesome presentation named *[In the Loop][In the Loop]*. 
You'll enjoy that presentation.

#TODO: WSGI. Communication between HTTP server and Django
## Django

#TODO: Communication between spring-web and Jetty.
*Servlet* and *Servlet Container* spec.
[Servlet Spec][Servlet Spec]

#TODO: Execution model of Interpreted langs. and compiled langs.
#Ex: python and C








[Concurrency model and Event Loop]: https://developer.mozilla.org/en-US/docs/Web/JavaScript/EventLoop
[In the Loop]: https://www.youtube.com/watch?v=cCOL7MC4Pl0
[How JavaScript works: Event loop and the rise of Async programming + 5 ways to better coding with async/await]: https://blog.sessionstack.com/how-javascript-works-event-loop-and-the-rise-of-async-programming-5-ways-to-better-coding-with-2f077c4438b5
[PHP execution model vs Python web]: https://blog.xoxzo.com/2012/05/02/php-execution-model-vs-python-web/

[asynchronous]: https://www.webopedia.com/TERM/A/asynchronous.html

[Servlet Spec]: https://jcp.org/aboutJava/communityprocess/final/jsr340/index.html