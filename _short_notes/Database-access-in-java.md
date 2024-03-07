---
layout: post
title:  "Database access in Java"
description: "MySQL upgrade experience"
categories: ["database", "java", "sql"]
date: 07-03-2024
author: "Sai Kiran"
---
While working on a java micro-service that exposes REST APIs or a web application (that returns server-side rendered web pages to a "web browser"), or web application development in-general, we will have a requirement to access databases in Java.
There are wide variety of frameworks to ease the database access in Java. For example, JDBC, Hibernate, Spring JPA, mybatis etc. I was confused why we have these many frameworks and which one to use when.
I've worked in a project that uses mybatis for database access and hibernate as well (long time back). For me, [Java & Databases: An Overview of Libraries & APIs](https://web.archive.org/web/20240127202222/https://www.marcobehler.com/guides/java-databases) helped me to understand various frameworks or libraries and when to use them. I came to know that blog while going through [What is MyBatis?](https://web.archive.org/web/20240109210529/https://mybatis.org/mybatis-3/), also [Philosophy and Apology](https://web.archive.org/web/20231130234426/https://mybatis.org/generator/philosophy.html) from MyBatis has a good use case to understand. 

Learnings:
1. How the database access is done in various java projects, which library or framework is suitable for the specific case and overview of existing libraries and frameworks.
2. Client side rendering: REST APIs are exposed through service, at client side, javascript will generate(or render) HTML page and then "visually rendered by the browser". Libraries like React is used in this setup.
3. Server side rendering: The service will return a fully constructed HTML page (of course javascript files will be required to define various actions and modifications to the HTML document). This HTML page is constructed at server side. Applications will use templates to generate the response.
4. Static site generation, is a server side rendering of pages, so that there won't be dynamic process required to generate the response.

This is a rough notes to record my learnings.