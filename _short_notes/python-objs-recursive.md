---
layout: post
title:  "Pythons objects can be recursive"
description: "Pythons objects can be recursive"
categories: ["tech"]
date: 11-05-2024
author: "Sai Kiran"
---

Python objects can be recursive! for example, to a list you can add itself as an element.
> a = [1,2,3] 

>  a.append(a)

> print(a)

Python's [copy](https://docs.python.org/3/library/copy.html) module highlights this problem. 