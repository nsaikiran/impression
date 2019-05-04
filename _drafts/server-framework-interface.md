---
layout: post
title:  "Behind the magic curtains: Web server interfaces"
description: "Interaction between web server and application code"
categories: ["tech"]
tags: ["web"]
author: "Sai Kiran"
---


*To understand the web server interfaces, we need to understand why we need then in the first place
and what are we interfacing with.*

*Lot of services are added to the web day by day.
While web app developing we come across terms like, 
web server, application 
server, web 
frameworks among serveral others. While programming the application, whatever the language it may
 be,
 we assume that a web request is handed over to us and we focus on generating a web response. 
This time we'll try to understand
This is an attempt to be convinced with whatever I've been doing.*
 
*These days while developing web applications, 
we'll assume we have request and focus on generating a response.
We don't need to bother how our application code is invoked with necessary data.
How a web server communicates with our code is taken for granted.
This time we'll try explore how web server interacts with our application code.*

Looking at the evolution of HTTP and HTML gave me a good understanding.

HTTP and HTML have evolved a lot to accommodate the needs of web.

The linked nature of [HTML](https://developer.mozilla.org/en-US/docs/Web/HTML) documents 
introduced the word "web". Web is continuosly evolving since its inception. When you get 
questions like "why certains things are the way thery are right now"? the answer lies in 
evolution process. HTTP and HTML being major building blocks of the web. Understand their 
evolution clarifes some questions. Most of the times I wanted to be convinced about the terms used.
Understanding those terms gives lot of insights. FOr example, I wanted have a convincing 
explanation of terms like web server, application server, web frameworks. We also need to 
understand that usage of those terms are bound to some "context", some terms may be irrelavent in 
the course of evolution. Now I'll share how I got convincing explanation for the those terms.


To understand those terms, we need to look at the evolution of HTTP. It is a simple protocol. 
Check the [Evolution of HTTP](https://developer.mozilla.org/en-US/docs/Web/HTTP/Basics_of_HTTP/Evolution_of_HTTP)
to understand more.

Server program that commuincates in HTTP is HTTP Server.

We'll focus on HTTP. As initial version of HTTP has only GET verb, the http server need just to 
serve 
some static HTML document that is stored on disk and send it to client.

With later versions, HTTP got extended with more verbs and header fields.

Over the web, resources(document, blog post, user, etcs) are identified. operations of those 
HTTP verbs standardize the operations on those resources.

We have server software that provides access to the resources it has. They are HTTP servers. You 
can write your own HTTP Server in any favorite language.

HTTP Server should understand the HTTP verbs and carryout operation enforced by the HTTP verb on 
specified entity. ** list verbs**.


**TODO: Picture with server + application cod**
![server-application]({{'/assets/images/server-interface/server application.jpeg' | absolute_url }})

Now the resources are simply not pre-generated static files. They might be stored in a database. 
You are giving access to those resources. HTTP servers can give access to pre-generated files or 
resouces that are dynamic. For every request of a resource, we'll need to query the disk/database
 and do the specified operation. This is called dynamic response generation. You might be 
 generating JSON representation or HTML document or any representation that the client requested 
 for. Now your HTTP Server application contain code that takes in requests from internet and code
  that know how to operate on our resources according to the verbs. Server code and application 
  code.
  
When the complexity of application code and requirements of the web are increasing.

We wanted to focus on each of individual tasks. Those are that part that takes in requests and 
the one generating and dynamic response.

![server-application]({{'/assets/images/server-interface/seperation.jpg' | absolute_url }})

We have web frameworks that aid us programming the dynamic response generation part. and 
specialized server that can handle all technical complexity of being entry point to the web.


As we are separating the serving functionality from application code, the requirement to 
understand the HTTP verbs has been moved to the application code. Your appplication code needs to
 understand the verbs not the serving part. That is the whole part.


Now when you seperate these things, you need to connect them, right.
One that is entry point to your sevice and another piece is the service itself. 
The service can be just few scripts, or it can be a HTTP Server that fully understands the verbs 
and process the requests.

Connecting the server part and application:

CGI 
FastCGI
Proxy pass etc.,


We call those serving entities that focuses on ever increasing technical complexities of being the
entry point to services: taking maximum number of requests, protecting from the attacks, 
effective handling of static files, buffering response to clients with low bandwidth, HTTPS 
support, etc.,
They are called as web servers. The gate keepers of our services to the web.
Famous web servers out there are nginx, apache and IIS. The features of these web servers are 
just a configuration away. These web server may not understand the request.


If you have another server which serves the application code, that can be called as application 
server. This servers need not support all the above mentioned features of web servers. They are 
supposed handle the request that are forwareded.



The serving part is web server. Web servers are keeper of gates.
 

 

 



When we look at HTTP verbs creates expectation. Over the web we'll identify the resources 


 
HTTP is used to as communication protocl.
Those documents are served to the user and user explores web using 
a webclient.
makes the internet 
"web". 
documents are linked. using client you explore the web.
If you check 
clarifies the 

extra [Brief history of HTTP](https://hpbn.co/brief-history-of-http/)


[Understanding HTTP PUT](https://www.w3.org/blog/2008/10/understanding-http-put/)
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
- [Apache, FastCGI and Python](https://www.electricmonk.nl/docs/apache_fastcgi_python/apache_fastcgi_python.html)
- [Understanding uwsgi, threads, processes, and GIL](https://www.reddit.com/r/Python/comments/4s40ge/understanding_uwsgi_threads_processes_and_gil/)

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
A server that contains your application code can be called as `application server`. Sometimes 
they may not use HTTP protocol, or they may use multiple protocols based on requirement, or they 
may even use proprietary protocols.
 
You may have a HTTP Server that exposes RESTful APIs for application code. You can call that as 
`application server`.

People use the term *application server*, to distinguish the HTTP Server executing dynamic 
response generation from the web server that is used as a reverse proxy. 

**Other useful links**:
- [Application Server vs. a Web Server?][difference]

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
