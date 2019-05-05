---
layout: post
title:  "Behind the magic curtains: Web server interfaces"
description: "Interaction between web server and application code"
categories: ["tech"]
tags: ["web"]
author: "Sai Kiran"
---


*While developing web applications, 
we assume that we have request and focus on generating a response.
The request reaches the application code through a web server.
How a web server communicates with the application code is taken for granted.
This writing is the result of my attempts to understand communication between web server and 
application code.*

----

To understand web server interfaces, I had to understand terms like web server, 
application code, dynamic response generation, web framework and application server. 
To understand these terms 
I needed to go through the evolution of web. 

# The need for interfaces
*Server* process is an example of *[daemon](http://www.linfo.org/daemon.html)*. 
It continuously serves its clients.
A server that communicates using [HTTP](https://www.w3.org/Protocols/rfc2616/rfc2616.html) is 
*HTTP Server*. 
As initial version of HTTP has only GET 
verb, the HTTP Server needed to serve some static HTML documents that are stored on disk.
With the later versions, [HTTP got extended](https://developer.mozilla.org/en-US/docs/Web/HTTP/Basics_of_HTTP/Evolution_of_HTTP) with more verbs and header fields.

Let us say we have *a web service*, through which the resources are made available to the web. 
As [HTTP verbs](https://www.w3.org/Protocols/rfc2616/rfc2616-sec9.html) standardize the operations 
on the resources of the web, the web service should understand the HTTP verbs to carryout 
operation 
enforced by the HTTP verb on 
the specified entity. 
Now, the resources are not pre-generated static files. New resources can be created and existing 
ones can be updated or removed. 
Hence, for every request we need to generate the response 
dynamically &mdash; may be by querying the database. This is called *dynamic response generation*. 
For example, JSON representation or HTML document or any specific representation of a 
resource can be generated. 

Hence, the web service application should contains two parts: code that responds to internet by 
taking in 
requests 
and sending out response, and code that operates on our resources according to the verbs.
The former is HTTP Server code and the latter is *application code*.


![web service]({{'/assets/images/server-interface/web service.jpg' | absolute_url }})


Soon, the "technical" expectations of the servers changed; they are expected to be 
very fast and robust. The application code started to become complex; development teams needed 
help. Now, there are two problems to solve: developing servers capable of serving the needs modern 
web,
and developing tools for manageable web application development.
Significant efforts have been made in to producing specialized solutions to these two problems.
 
To solve the former problem, people started building "generic" server software.
They called it as a "web server".
[The reason behind nginx creation](https://www.aosabook.org/en/nginx.html) describes the expectations of a modern web server. 
Some of those expectations are: the ability to handle maximum number of requests per unit time, 
protecting the resources from the attacks, effective handling of static files, 
buffering response to clients with low bandwidth, HTTPS support, etc.,
 
To solve the latter problem, people started to building *web frameworks* to simplify the dynamic 
response generation. 
 
![web service seperated into server and application]({{'/assets/images/server-interface/server-application.jpg' | absolute_url }})

Web servers are the qualified gate keepers of our services.
Famous web servers out there are [nginx](https://www.nginx.com/), 
[apache](https://httpd.apache.org/) and [IIS](https://www.iis.net/). 
The features of these web servers are just a *configuration* away. 

As the goal of web servers is not to "understand" the request &mdash; for them every request is 
equivalent to a GET request, application code is expected to 
 understand the request and carryout the necessary operation. 
 HTTP verbs should drive the application code.


#### Useful links:
- [Brief history of HTTP](https://hpbn.co/brief-history-of-http/)
- [Understanding HTTP PUT](https://www.w3.org/blog/2008/10/understanding-http-put/)
- [What is a web server?][webserver]
- [Build your own web server](https://github.com/danistefanovic/build-your-own-x#build-your-own-web-server)


# Interfaces
Once we have a web server and a application, we need to *interface* them.
As the web server are "generic", any application can be interfaced. 
But the interfacing methods depend on the type of the application. 
For example, the application can be a group of *script files* or a standalone service.

![web server interface]({{'/assets/images/server-interface/interface.jpg' | absolute_url }})

Below are some widely used interfaces:
- [CGI](https://tools.ietf.org/html/rfc3875)
- [FastCGI](http://www.mit.edu/~yandros/doc/specs/fcgi-spec.html)
- [Reverse Proxy](https://en.wikipedia.org/wiki/Reverse_proxy)

Sometimes a programming language community might come up with their own standard.
Python community came up their own standard, called WSGI to be used for communication between 
web server and python application. WSGI implementations are available for major web servers.

If the application itself is a standalone service, then it can be called as an *application 
server*. 
An application server, which runs the application code can be a HTTP Server without the 
qualities of a web 
server.
A web server can be configured to be reverse proxy to the application server. [Usage of the term *application server* 
can be contextual.](https://howtodoinjava.com/tomcat/a-birds-eye-view-on-how-web-servers-work/)

# Application
We can program the web application in any programming language. To aid the web application 
development, many web frameworks are available. `django` in Python and `Spring` in Java are 
examples of web 
frameworks.
Some web frameworks provide you with a [*development server*](https://docs.djangoproject.com/en/2.2/intro/tutorial01/#the-development-server) to avoid the overhead of 
installing a web server during development. 
Production ready web server must be used to open traffic from the web.

Examples of web application development:
### Python:
- [How to Use Python in the web](https://docs.python.org/2/howto/webservers.html)
- [An introduction into the WSGI ecosystem](https://www.ultravioletsoftware.com/single-post/2017/03/23/An-introduction-into-the-WSGI-ecosystem)
- [uWSGI](https://uwsgi-docs.readthedocs.io/en/latest/index.html)
- [Apache, FastCGI and Python](https://www.electricmonk.nl/docs/apache_fastcgi_python/apache_fastcgi_python.html)
- [Understanding uwsgi, threads, processes, and GIL](https://www.reddit.com/r/Python/comments/4s40ge/understanding_uwsgi_threads_processes_and_gil/)

### Java:
Currently, Servlets is the standard way of web development in Java. 
Spring, one of the widely used framework for web development implements Servlets standard.

Application code written using Servlets is deployed using HTTP servers written in Java.
These servers contain *servlet container* component to invoke the application code written 
using Servlets. 
Jetty and tomcat are examples of servers used to to deploy servlet code. 
These servers can be called as *application servers*.

#### Useful links:
- [How web servers work?](https://howtodoinjava.com/tomcat/a-birds-eye-view-on-how-web-servers-work/)
- [Servlet Specification](https://javaee.github.io/servlet-spec/downloads/servlet-4.0/servlet-4_0_FINAL.pdf)
- [List of Web Containers](https://en.wikipedia.org/wiki/Web_container).

-----

#### Useful links:
- [HTML](https://developer.mozilla.org/en-US/docs/Web/HTML) 
- [Common Questions](https://developer.mozilla.org/en-US/docs/Learn/Common_questions)
- [server-side](https://developer.mozilla.org/en-US/docs/Learn/Server-side)
- [Web technology for developers](https://developer.mozilla.org/en-US/docs/Web)
- [Application Server vs. a Web Server?][difference]
- [Web Characterization Terminology & Definitions Sheet](https://www.w3.org/1999/05/WCA-terms/)

*Behind the magic curtains* is a series of writings. 
Checkout [Behind the magic curtains: Spring Boot]({{'tech/2017/10/07/Spring-Boot.html' | absolute_url}})


[webserver]: https://developer.mozilla.org/en-US/docs/Learn/Common_questions/What_is_a_web_server
[nginx]: https://www.nginx.com/resources/glossary/nginx/
[difference]: https://www.nginx.com/resources/glossary/application-server-vs-web-server/


[comment]: <> (Windows: Internet Server Application Programming Interface)  
