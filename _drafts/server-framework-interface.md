---
layout: post
title:  "Behind the magic curtains: Web server interfaces"
description: "Interaction between web server and application code"
categories: ["tech"]
tags: ["web"]
author: "Sai Kiran"
---

*These days while developing web applications, 
We'll assume we have request and focus on generating a response.
We don't need to bother how our application code is invoked with necessary data.
How a web server communicates with our code is taken for granted.
This time we'll try explore how web server interacts with our application code.*
-----

While exploring the bridge between web server and application code, being clear on 
certain terms is necessary.

# Web Server

The *server* process is an example of *[daemon](http://www.linfo.org/daemon.html)*. It continuously serves its clients.

A server that communicates using HTTP is *HTTP Server*.

Most of the times web server and http server are interchangeable. 
But Web server is a HTTP server with other features that addresses issues 
found in the internet. For example, security, high concurrency, resource friendly, compression 
and handling static content effectively.

For implementing a basic HTTP Server in your favorite language, refer [Build Your Own X](https://github.com/danistefanovic/build-your-own-x#build-your-own-web-server)

Apache and Nginx are standard web server I've used. 
I was going through [the reason behind nginx creation](https://www.aosabook.org/en/nginx.html) 
and came to know the expectations of modern web servers.

Initially web servers are designed for serving the static contents. At that time we dn't 
even have many verbs. Explore evolution of HTTP to know more.
Web Servers evolved with HTTP. But now we have more verbs and 
the URL may not representing static content. For every request, 
response may need to be dynamically generated. Being able to serve dynamic response is also 
an expectation of web server.

Other useful links:
- [web server][webserver]

# Application code:
As there is a requirement for dynamic response generation, 
we'll program your logic in your a lang.

Now we have webframeworks, facilitating us to generate dynamic content in our own favorite 
language we choose.
Now we have frameworks available to help us in quick development and provides lot of boilerplate 
code in our fav languages. we focus of generating response based on our business logic.
You can browse for web frame works in language you work. To name few, django in Python, Spring in
 Java etc.
 
In the application code you assume you get a representation of request and you return 
representation of response. And focus on converting request to response.
Who defines/converts actual http request/response to the representaion suitable for you. Those 
are interfaces.
some frameworks will provide a builtin HTTPserver software for dev purpose only. You need to 
use  a  production ready webserver later.

# Interfaces:
Now we will extend the web server that can serve static content so well and standard features. 
for dynamic responses. These two are some of interfaces.

- [CGI](https://tools.ietf.org/html/rfc3875)
- [FastCGI](http://www.mit.edu/~yandros/doc/specs/fcgi-spec.html)

Major web servers have extensions implemented for the language you choose

[CGI, FCGI](https://stackoverflow.com/questions/3937224/differences-and-uses-between-wsgi-cgi-fastcgi-and-mod-python-in-regards-to-py)

Sometiems programming language community might come up with their own standard.
Python community has come up their own standard, called WSGI to be used for communication between 
webserver and python application.

Now once you have your code ready you need to serve your clients. 
So there are webserver implementaions in the language we choose to program our web application.
So you can use that webserver implemented in your own language to run the dynamic content 
genration code we've written. That would be easier. By the way writing a plain simple webserver 
in your favorite language is not that hard. 

Also while using other software, there will be a need to proplerly understand how it wll be used 
and configure it. 

Then there are standards to connect your web frameworks and web severs in each language you choose.

### Python:
- [HOWTO Use Python in the web](https://docs.python.org/2/howto/webservers.html)
- [An introduction into the WSGI ecosystem](https://www.ultravioletsoftware.com/single-post/2017/03/23/An-introduction-into-the-WSGI-ecosystem)
- [uWSGI](https://uwsgi-docs.readthedocs.io/en/latest/index.html)

### Java:
Currently, Servlets is the standard way of web dev in Java.
For application code written in Java, servlet containers takes care of interfacing.
Jetty and tomcat are examples.
They takes care of communication in HTTP with outside world and invoking your application code 
written using Servlet api.

Incase of Java we have servlet container like Jetty, tomcat and several of them to connect 
forward the requests to your application code written using a web framework.

JAVA: https://en.wikipedia.org/wiki/Web_container

Windows: Internet Server Application Programming Interface ?
Examples:

When directly working woth spring boot, we are taking everytihg granted. development is is easy. 
But the underlying setup is this.

Other useful links:
- [How web servers work?](https://howtodoinjava.com/tomcat/a-birds-eye-view-on-how-web-servers-work/)

# App server:
[app vs web server][difference].
The confusion starts because, in most of scenarios both the web server and app server talk HTTP.
Your app server maybe a http server which only generated JSON response.

Application server not necessarily talk in HTTP. It may support more than one protocol. They may 
talk in a proprietery protocol to serve proprietery clients. 

But these days people use this term to distinguish more then one HTTPServer that is being used.
You may use a reverseproxy/load balancer for all other non-business requirements and use a server
 that also talks HTTP but serves your business logic.

-----
Evolution is the answer for why some things are in certain way. Explore the evolution.

Other useful links:
- [Common Questions](https://developer.mozilla.org/en-US/docs/Learn/Common_questions)
- [server-side](https://developer.mozilla.org/en-US/docs/Learn/Server-side)
- [Web technology for developers](https://developer.mozilla.org/en-US/docs/Web)

[webserver]: https://developer.mozilla.org/en-US/docs/Learn/Common_questions/What_is_a_web_server
[nginx]: https://www.nginx.com/resources/glossary/nginx/
[difference]: https://www.nginx.com/resources/glossary/application-server-vs-web-server/

