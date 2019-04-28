---
layout: post
title:  "Behind the magic curtains: Web server interface"
description: "How web server and web-framework interact"
categories: ["tech", "cs"]
tags: ["execution-models"]
author: "Sai Kiran"
---

Wanted to correct the way I use webserver,app server.

*These days while developing web applications, I didn't mind how the request comes till my 
application code, we assume the we have a request and focus on generating response. But there are
 lot of things in the middle. How webserver communicates with our code is taken for granted.
 This time we'll try to learn. Also wanted to understand the terms we use in the process. 
 Properly understanding the context behind each terms is very important.*

-----

# Web Server

[web server][webserver], app server.
I think the *server* process is an example of `daemon`. It continuously serves its clients.
server that understand HTTP is *HTTPServer*. You can write your own http server. (link).

Build your own webserver in [Building webserver](https://github.com/danistefanovic/build-your-own-x#build-your-own-web-server)

Most of the times web server and http server are interchageable.

It is easy to write a webserver in your fav language. But these days webservers need to provide lot
 of functionaltiy for that use well develped ones.  I would think the web server gives you lot of
  general capabilities that can used out of the box. Like securites measures, static content 
  serving best way. I think web servers are http servers that serves content for web browser use,
   because most of the http headers are obeyed by browsres if not all clients.
   
If a server delivers web content. that is webserver? Most of webserver talk HTTP. 
I happen to read [nginx](https://www.aosabook.org/en/nginx.html). understood many aspects that a 
web server needs to deal with. They do lot of things in good way.

Initially web servers are designed for serving the static contents. Initially the web content 
used to be static. But now the requirements are 
more and we need dynamic content. URL is not representing static content. it represents dynamic 
response.

dynamic response need to be generated programatically. Many efforts are made to produce dynamic 
content.

So a static web server is generally assumes the resources as static and serves them as-is.

Previously people used to extend the functionality of static webserver by extending it, to serve 
the dynamic content. A technique was to use CGI standard. where in some scripts are executed to get 
get the dynamic content. Lot of scripting languages supported that feature, like python and perl 
etc.,


# Application code:
Now for generating the dynamic response to the client. YOu'll program your logic in your a 
language you choose. 
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
Se

# App server:
[app vs web server][difference].
The confusion starts because, in most of scenarios both the web server and app server talk HTTP.
Your app server maybe a http server which only generated JSON response.

Application server not necessarily talk in HTTP. It may support more than one protocol. They may 
talk in a proprietery protocol to serve proprietery clients. 

But these days people use this term to distinguish more then one HTTPServer that is being used.
You may use a reverseproxy/load balancer for all other non-business requirements and use a server
 that also talks HTTP but serves your business logic.

--- 
Evolution is the answer for why some things are in certain way. Explore the evolution.

Other useful links:
- [Common Questions](https://developer.mozilla.org/en-US/docs/Learn/Common_questions)
- [server-side](https://developer.mozilla.org/en-US/docs/Learn/Server-side)
- [Web technology for developers](https://developer.mozilla.org/en-US/docs/Web)

[webserver]: https://developer.mozilla.org/en-US/docs/Learn/Common_questions/What_is_a_web_server
[nginx]: https://www.nginx.com/resources/glossary/nginx/
[difference]: https://www.nginx.com/resources/glossary/application-server-vs-web-server/

