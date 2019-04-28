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

I think the *server* process is an example of `daemon`. It continuously serves its clients.
server that understand HTTP is *HTTPServer*. You can write your own http server. (link).

It is easy to write a webserver in your fav language. But these days webservers need to provide lot
 of functionaltiy for that use well develped ones.  I would think the web server gives you lot of
  general capabilities that can used out of the box. Like securites measures, static content 
  serving best way.

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
the application server is used to produce dynamic content based the context of request.

Previously people used to extend the functionality of static webserver by extending it, to serve 
the dynamic content. A technique was to use CGI standard. where in some scripts are executed to get 
get the dynamic content. Lot of scripting languages supported that feature, like python and perl 
etc.,


# Application code:
Now we have webframeworks, facilitating us to generate dynamic content in our own favorite 
language we choose.


Now we have frameworks available to help us in quick development and provides lot of boilerplate 
code in our fav languages. we focus of generating response based on our business logic.

Like if you want to program your dynamic content genration in Java, there are framework, the one 
I'm aware and used is Spring. Incase of Python I've used django a bit. and in ruby I've heard 
rails is one of the frameworks.

In django HTTpreuest object we get and produce HTTPresponse.

the interface takes care of converting it.

Flow in framework is another topic.
Flow till framework is done by a interface. These interfaces are well defined for each language.

some frameworks will provide a builtin HTTPserver software for dev purpose only. You need to 
use  a  production ready webserver later.

# App server:

[app vs web server][difference].
The confusion starts because both of them speak HTTP.
Your app server maybe a http server which only generated JSON response.


Application server not necessarily talk in HTTP. It can talk in many protocols as required. For 
me application server is designed for your specific purpose. It may speak HTTP, SMTP, FTP and 
more based on your requirement. It may provide many services.


# Interfaces:

Interfaces are standardized based on which web server you are using, which laguage your app code 
is in. several factors.

For dynamic response generation we have facility scripts written for response generations.
That is CGI. People used to generate dynamic response with scripts written many 
interpreted/scripting langs.

Because of limitations they come up with FastCGI. Improved versions.


Web dev in python [web dev](https://docs.python.org/2/howto/webservers.html) 
 
 FOr example in pytohn writing server.
 
 Build your own webserver in [Building webserver](https://github
 .com/danistefanovic/build-your-own-x#build-your-own-web-server)

WSGI for python. [An introduction into the WSGI ecosystem](https://www.ultravioletsoftware.com/single-post/2017/03/23/An-introduction-into-the-WSGI-ecosystem)
Servlet container will do in JAVA.
etc.


Python WSGI complaint server [uWSGI](https://uwsgi-docs.readthedocs.io/en/latest/index.html)

Also while using other software, there will be a need to proplerly understand how it wll be used 
and configure it. 

[CGI, FCGI](https://stackoverflow.com/questions/3937224/differences-and-uses-between-wsgi-cgi-fastcgi-and-mod-python-in-regards-to-py)

[HOWTO Use Python in the web](https://docs.python.org/2/howto/webservers.html)

Why we have so many server implementations? Here I'm talking about webserver implementations.
I've heard and used apache, a veteran webserver and nginx a new one. These are mainstream 
webservers.

But then we also have application servers. 

So started understanding meaning of those words. [web server][webserver], app server.


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


The differences between server, webserver and application server


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


Evolution is the answer for why some things are in certain way. Explore the evolution.


https://developer.mozilla.org/en-US/docs/Learn/Common_questions
https://developer.mozilla.org/en-US/docs/Learn/Server-side
https://developer.mozilla.org/en-US/docs/Learn/Server-side/First_steps/Introduction
https://developer.mozilla.org/en-US/docs/Web

[webserver]: https://developer.mozilla.org/en-US/docs/Learn/Common_questions/What_is_a_web_server
[nginx]: https://www.nginx.com/resources/glossary/nginx/
[difference]: https://www.nginx.com/resources/glossary/application-server-vs-web-server/

