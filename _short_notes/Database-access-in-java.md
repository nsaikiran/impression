---
layout: post
title:  "Database access in Java"
description: "MySQL upgrade experience"
categories: ["database", "java", "sql"]
date: 07-03-2024
author: "Sai Kiran"
---
## Introduction
While working on a java micro-service that exposes REST APIs or a web application (that returns server-side rendered web pages to a "web browser"), or web application development in-general, we will have a requirement to access databases in Java.
There are wide variety of frameworks to ease the database access in Java. For example, JDBC, Hibernate, Spring JPA, mybatis etc. I was confused why we have these many frameworks and which one to use when.
I've worked in a project that uses mybatis for database access and hibernate as well (long time back). For me, [Java & Databases: An Overview of Libraries & APIs](https://web.archive.org/web/20240127202222/https://www.marcobehler.com/guides/java-databases) helped me to understand various frameworks or libraries and when to use them. I came to know that blog while going through [What is MyBatis?](https://web.archive.org/web/20240109210529/https://mybatis.org/mybatis-3/), also [Philosophy and Apology](https://web.archive.org/web/20231130234426/https://mybatis.org/generator/philosophy.html) from MyBatis has a good use case to understand. 

## Other references
- [Hibernate - vs JDBC vs JPA vs Spring Data JPA](https://dev.to/yigi/hibernate-vs-jdbc-vs-jpa-vs-spring-data-jpa-1421)