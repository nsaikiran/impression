---
layout: post
title:  "Behind the magic curtains: Web server interfaces"
description: "Interaction between web server and application code"
categories: ["tech"]
tags: ["web"]
author: "Sai Kiran"
---


*To understand the web server interfaces, we need to understand why we needed them and what are we 
interfacing web servers with.*

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

Understanding the evolution process helps to get certain questions clarified.
For example, I have questions about the terms like web server, application server, web frameworks. 
And needed convincing answers. 
We need to keep in mind that usage of some terms are bound to certain "context", 
some terms may become irrelavent in the course of evolution.


The linked nature of [HTML](https://developer.mozilla.org/en-US/docs/Web/HTML) documents 
introduced the word "web". Web is continuosly evolving since its inception.  
HTTP and HTML being major building blocks of the web, understand their 
evolution clarifes some questions.

Now I'll share how I got convincing explanation for the those terms.

To understand those terms, we need to focus on  to the [Evolution of HTTP](https://developer.mozilla.org/en-US/docs/Web/HTTP/Basics_of_HTTP/Evolution_of_HTTP)


# Need for interfaces

The *server* process is an example of *[daemon](http://www.linfo.org/daemon.html)*. 
It continuously serves its clients.
A server that communicates using HTTP is *HTTP Server*.
For implementing a basic HTTP Server in your favorite language, refer [Build Your Own X](https://github.com/danistefanovic/build-your-own-x#build-your-own-web-server)

As initial version of HTTP has only GET 
verb, the http server need just to 
serve some static HTML document that is stored on disk and send it to client.
With later versions, HTTP got extended with more verbs and header fields.

HTTP verbs standardize the operations on the resources of the web.
HTTP Server should understand the HTTP verbs and carryout operation enforced by the HTTP verb on 
specified entity. **list verbs**. 

Now, the resources are not pre-generated static files. 
They might be stored in a database. The operations are carried out on those resources.
Hence, for every request we need to generate the response 
dynamically &mdash may be by querying the database. This is called dynamic response generation. 
For example, JSON representation or HTML document or any specific representation of a 
resource can be generated. 

Hence, the HTTP Server application should contains two parts: code that responds to internet by 
taking in 
requests 
and sending out response, and code that operates on our resources according to the verbs.
We name the code that actually operates on resources as *application code*.


![server-application]({{'/assets/images/server-interface/server application.jpeg' | absolute_url }})
server + application code


Soon, the "technical" expectations of the servers changed. For example, they are expected to be 
very fast and robust. The application code started to become complex. Development teams needed 
help. Now there are two problems to solve: developing servers with ever increasing "technical 
expectations" met, and developing tools for manageable web application development.
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

Web servers are the keepers of our services to the web.
Famous web servers out there are nginx, apache and IIS. 
The features of these web servers are 
just a configuration away. 

As the goal of web servers is not to "understand" the request, for them every request is 
equivalent to a GET request. Application code is responsible to
 understand the request and carryout the necessary operation. HTTP verbs drive our application code.

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

A HTTP Server, which may not possess all the qualities that of a web server can be used to run 
the application code. This HTTP Server can be called as *application server*. Web server can be 
configured to be reverse proxy to the application server. [Usage of the term *application server* 
can be contextual.](https://howtodoinjava.com/tomcat/a-birds-eye-view-on-how-web-servers-work/)

# Application
We can program the web application in any programming language. We have many web frameworks 
available in major languages. `django` in Python and `Spring` in Java are examples of web 
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

Application code written using Servlets is deployed using web servers written in Java.
These web servers contain *servlet container* component to invoke the application code written 
using Servlets. Jetty and tomcat are web servers to name a few. For full list refer 
[List of Web Containers](https://en.wikipedia.org/wiki/Web_container) 



The service can be just few scripts, or it can be a HTTP Server that fully understands the verbs 
and process the requests.

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

**Other useful links**:
- [web server][webserver]

**Other useful links**:
- [How web servers work?](https://howtodoinjava.com/tomcat/a-birds-eye-view-on-how-web-servers-work/)
- [Servlet Specification](https://javaee.github.io/servlet-spec/downloads/servlet-4.0/servlet-4_0_FINAL.pdf)


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
