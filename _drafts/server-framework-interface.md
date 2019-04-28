---
layout: post
title:  "Behind the magic curtains: Web server interfaces"
description: "Interaction between web server and application code"
categories: ["tech"]
tags: ["web"]
author: "Sai Kiran"
---

*These days while developing web applications, 
we'll assume we have request and focus on generating a response.
We don't need to bother how our application code is invoked with necessary data.
How a web server communicates with our code is taken for granted.
This time we'll try explore how web server interacts with our application code.*


-----

While exploring the bridge between web server and application code, we'll also try to understand 
certain terms.

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

**Other useful links**:
- [web server][webserver]

# Application code:
As there is a requirement for dynamic response generation, 
we'll program the logic in any chosen language.

We also have lot of web frameworks to assist and simplify our task of generating dynamic content 
for the request.
You can browse for web frame works in language you work. 
To name few, `django` in Python, `Spring` in Java etc.
 
In the application code, we assume that we have a representation of request and we will focus 
on generating a representation of response.

some frameworks will provide a builtin HTTPserver software for dev purpose only. You need to 
use  a  production ready webserver later.

# Interfaces:
The web server interface defines/converts actual 
http request/response to the required representation. 

There are several standards of interfaces. 
Below standards are supported in many languages. 
- [CGI](https://tools.ietf.org/html/rfc3875)
- [FastCGI](http://www.mit.edu/~yandros/doc/specs/fcgi-spec.html)

Explore more about them to know more technical details.

Sometimes a programming language community might come up with their own standard.
Python community has come up their own standard, called WSGI to be used for communication between 
web server and python application. WSGI implementations are available for major web servers.

As a fun task, take a web server written in the language you work, and extend its functionality 
with your application code.

### Python:
- [How to Use Python in the web](https://docs.python.org/2/howto/webservers.html)
- [An introduction into the WSGI ecosystem](https://www.ultravioletsoftware.com/single-post/2017/03/23/An-introduction-into-the-WSGI-ecosystem)
- [uWSGI](https://uwsgi-docs.readthedocs.io/en/latest/index.html)

### Java:
Currently, Servlets is the standard way of web development in Java. 
Spring, one of the widely used framework for web development implements Servlets standard.

Application code written using Servlets is deployed using web servers written in Java.
These web servers contain *servlet container* component to invoke the application code written 
using Servlets. Jetty and tomcat are web servers to name a few. For full list refer 
[List of Web Containers](https://en.wikipedia.org/wiki/Web_container) 

**Other useful links**:
- [How web servers work?](https://howtodoinjava.com/tomcat/a-birds-eye-view-on-how-web-servers-work/)
- [Servlet Specification](https://javaee.github.io/servlet-spec/downloads/servlet-4.0/servlet-4_0_FINAL.pdf)

# App server:
[app vs web server][difference].

A server that contains your application code can be called as `application server`. Sometimes 
they may not use HTTP protocol, or they may use multiple protocols based on requirement, or they 
may even use proprietary protocols.
 
You may have a HTTP Server that exposes RESTful APIs for application code. You can call that as 
`application server`.

But these days people use this term to distinguish more then one HTTPServer that is being used.
For example you can use nginx web server a load balancer/reverse proxy and a HTTP Server to 
server your business logic.

-----
Evolution is the answer for why some things are in certain way. Explore the evolution.

**Other useful links**:
- [Common Questions](https://developer.mozilla.org/en-US/docs/Learn/Common_questions)
- [server-side](https://developer.mozilla.org/en-US/docs/Learn/Server-side)
- [Web technology for developers](https://developer.mozilla.org/en-US/docs/Web)

[webserver]: https://developer.mozilla.org/en-US/docs/Learn/Common_questions/What_is_a_web_server
[nginx]: https://www.nginx.com/resources/glossary/nginx/
[difference]: https://www.nginx.com/resources/glossary/application-server-vs-web-server/


[comment]: <> (Windows: Internet Server Application Programming Interface)  
