---
layout: post
title:  "Behind the magic curtains: Web server interface"
description: "How web server and web-framework interact"
categories: ["tech", "cs"]
tags: ["execution-models"]
author: "Sai Kiran"
---
Wanted to correct the way I use webserver,app server.

Why we have so many server implementations? Here I'm talking about webserver implementations.
I've heard and used apache, a veteran webserver and nginx a new one. These are mainstream 
webservers.

But then we also have application servers. 

So started understanding meaning of those words. [web server][webserver], app server.
I happen to read [nginx](https://www.aosabook.org/en/nginx.html). understood many aspects that a 
web server needs to deal with.


So a static web server is generally assumes the resources as static and serves them as-is.
the application server is used to produce dynamic content based the context of request.

Previously people used to extend the functionality of static webserver by extending it, to serve 
the dynamic content. A technique was to use CGI standard. where in some scripts are executed to get 
get the dynamic content. Lot of scripting languages supported that feature, like python and perl 
etc.,


Now we have webframeworks, facilitating us to generate dynamic content in our own favorite 
language we choose.

Like if you want to program your dynamic content genration in Java, there are framework, the one 
I'm aware and used is Spring. Incase of Python I've used django a bit. and in ruby I've heard 
rails is one of the frameworks.


Now once you have your code ready you need to serve your clients. 
So there are webserver implementaions in the language we choose to program our web application.
So you can use that webserver implemented in your own language to run the dynamic content 
genration code we've written. That would be easier. By the way writing a plain simple webserver 
in your favorite language is not that hard. 



Then there are standards to connect your web frameworks and web severs in each language you choose.
To connect any webserver(may be many not be written in pyton) we have WSGI standard to connect 
the server and the framework code you've written.


Incase of Java we have servlet container like Jetty, tomcat and several of them to connect 
forward the requests to your application code written using a web framework.



 

And the qualities web-server should poses. and app server should poses. 

All those fancy terms of internet can be understood here. [links below]
server, web-server, web-framework. 


The differences between server, webserver and application server can be u


Python web applications/frameworks can be connected via WSGI. All WSGI compaliant webservers can 
be used.

PSGI : Perl Web Server Gateway Interface
WSGI :
JavaScript Gateway Interface:
Simple Common Gateway Interface: 
FastCGI
CGI:

JAVA: https://en.wikipedia.org/wiki/Web_container

Windows: Internet Server Application Programming Interface ?


Examples:

Django and other webservers. WSGI. Spring and server interaction


When directly working woth spring boot, we are taking everytihg granted. development is is easy. 
But the underlying setup is this.
Se

https://developer.mozilla.org/en-US/docs/Learn/Common_questions
https://developer.mozilla.org/en-US/docs/Learn/Server-side
https://developer.mozilla.org/en-US/docs/Learn/Server-side/First_steps/Introduction
https://developer.mozilla.org/en-US/docs/Web

[webserver]: https://developer.mozilla.org/en-US/docs/Learn/Common_questions/What_is_a_web_server
[nginx]: https://www.nginx.com/resources/glossary/nginx/

