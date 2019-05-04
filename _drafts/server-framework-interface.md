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
We don't need to bother how our application code is invoked with necessary data.
How a web server communicates with the application code is taken for granted.
This writing is result of my attempts to understand communication between web server and 
application code.*

----

To understand web server interfaces, I had to understand terms like web server, 
application server, dynamic response generation and web framework. To understand these terms 
I needed to go through the evolution of web. 

# The need for interfaces
*Server* process is an example of *[daemon](http://www.linfo.org/daemon.html)*. 
It continuously serves its clients.
A server that communicates using [HTTP](https://www.w3.org/Protocols/rfc2616/rfc2616.html) is *HTTP Server*.
For implementing a basic HTTP Server in your favorite language, refer [Build Your Own X](https://github.com/danistefanovic/build-your-own-x#build-your-own-web-server)

As initial version of HTTP has only GET 
verb, the HTTP Server need to serve some static HTML document that is stored on disk.
With later versions, [HTTP got extended](https://developer.mozilla.org/en-US/docs/Web/HTTP/Basics_of_HTTP/Evolution_of_HTTP) with more verbs and header fields.

[HTTP verbs](https://www.w3.org/Protocols/rfc2616/rfc2616-sec9.html) standardize the operations on the resources of the web.
HTTP Server should understand the HTTP verbs and carryout operation enforced by the HTTP verb on 
specified entity. 

Now, the resources are not pre-generated static files. 
They might be stored in a database. The operations are carried out on those resources.
Hence, for every request we need to generate the response 
dynamically &mdash; may be by querying the database. This is called dynamic response generation. 
For example, JSON representation or HTML document or any specific representation of a 
resource can be generated. 

Hence, the HTTP Server application should contains two parts: code that responds to internet by 
taking in 
requests 
and sending out response, and code that operates on our resources according to the verbs.
We name the code that actually operates on resources as *application code*.


![server-application]({{'/assets/images/server-interface/server application.jpeg' | absolute_url }})


Soon, the "technical" expectations of the servers changed; they are expected to be 
very fast and robust. The application code started to become complex; development teams needed 
help. Now there are two problems to solve: developing servers capable of serving the needs modern 
web,
and developing tools for manageable web application development.
Significant efforts have been made in to producing specialized solutions to these two problems.
 
To solve the former problem, people started building "generic" server software.
They called it as a "web server".
[The reason behind nginx creation](https://www.aosabook.org/en/nginx.html) describes the expectations of a modern web server. 
Some of those expectations are: the ability to handle maximum number of requests per unit time, 
protecting the resources from the attacks, effective handling of static files, 
buffering response to clients with low bandwidth, HTTPS support, etc.,
 
To solve the latter problem, people started to build web frameworks to help fasten the dynamic 
response generation. 
 
![server-application]({{'/assets/images/server-interface/seperation.jpg' | absolute_url }})

Web servers are the gate keepers of our services.
Famous web servers out there are [nginx](https://www.nginx.com/), 
[apache](https://httpd.apache.org/) and [IIS](https://www.iis.net/). 
The features of these web servers are just a *configuration* away. 

As the goal of web servers is not to "understand" the request &mdash; for them every request is 
equivalent to a GET request, application code is expected to 
 understand the request and carryout the necessary operation. 
 HTTP verbs drive our application code.


**Other useful links:**
- [Brief history of HTTP](https://hpbn.co/brief-history-of-http/)
- [Understanding HTTP PUT](https://www.w3.org/blog/2008/10/understanding-http-put/)
- [web server][webserver]


# Interfaces
Once we have web servers and application, we need to *interface* them.
As the web server are "generic", any application can be interfaced. But the interfacing methods 
depend on type of the application.

Below are some widely used interfaces:
- [CGI](https://tools.ietf.org/html/rfc3875)
- [FastCGI](http://www.mit.edu/~yandros/doc/specs/fcgi-spec.html)
- [Reverse Proxy](https://en.wikipedia.org/wiki/Reverse_proxy)

Sometimes a programming language community might come up with their own standard.
Python community has come up their own standard, called WSGI to be used for communication between 
web server and python application. WSGI implementations are available for major web servers.

A HTTP Server, which may not all the qualities that of a web server can be used to run 
the application code. This HTTP Server can be called as *application server*. Web server can be 
configured to be reverse proxy to the application server. [Usage of the term *application server* 
can be contextual.](https://howtodoinjava.com/tomcat/a-birds-eye-view-on-how-web-servers-work/)

# Application
We can program the web application in any programming language. To aid the web application 
development, many web frameworks are available. `django` in Python and `Spring` in Java are 
examples of web 
frameworks.
 
Some web frameworks provide you with a *development server* to avoid the overhead of installing a 
web server during development.

Examples of web application development:
#### Python:
- [How to Use Python in the web](https://docs.python.org/2/howto/webservers.html)
- [An introduction into the WSGI ecosystem](https://www.ultravioletsoftware.com/single-post/2017/03/23/An-introduction-into-the-WSGI-ecosystem)
- [uWSGI](https://uwsgi-docs.readthedocs.io/en/latest/index.html)
- [Apache, FastCGI and Python](https://www.electricmonk.nl/docs/apache_fastcgi_python/apache_fastcgi_python.html)
- [Understanding uwsgi, threads, processes, and GIL](https://www.reddit.com/r/Python/comments/4s40ge/understanding_uwsgi_threads_processes_and_gil/)

#### Java:
Currently, Servlets is the standard way of web development in Java. 
Spring, one of the widely used framework for web development implements Servlets standard.

Application code written using Servlets is deployed using HTTP servers written in Java.
These servers contain *servlet container* component to invoke the application code written 
using Servlets. 
Jetty and tomcat are servers used to to deploy servlet code. 
For full list refer [List of Web Containers](https://en.wikipedia.org/wiki/Web_container). 
These servers can be called as *application servers*.

Other useful links:
- [How web servers work?](https://howtodoinjava.com/tomcat/a-birds-eye-view-on-how-web-servers-work/)
- [Servlet Specification](https://javaee.github.io/servlet-spec/downloads/servlet-4.0/servlet-4_0_FINAL.pdf)

-----

**Other useful links**:
- [HTML](https://developer.mozilla.org/en-US/docs/Web/HTML) 
- [Common Questions](https://developer.mozilla.org/en-US/docs/Learn/Common_questions)
- [server-side](https://developer.mozilla.org/en-US/docs/Learn/Server-side)
- [Web technology for developers](https://developer.mozilla.org/en-US/docs/Web)
- [Application Server vs. a Web Server?][difference]


[webserver]: https://developer.mozilla.org/en-US/docs/Learn/Common_questions/What_is_a_web_server
[nginx]: https://www.nginx.com/resources/glossary/nginx/
[difference]: https://www.nginx.com/resources/glossary/application-server-vs-web-server/


[comment]: <> (Windows: Internet Server Application Programming Interface)  
