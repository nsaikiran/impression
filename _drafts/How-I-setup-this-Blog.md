---
layout: post
title:  "How I setup this blog"
categories: ["tech"]
author: "Sai Kiran"
---

Hosting a blog is possible because of [Github Pages][Link to Github Pages].
First I bought a `.blog` domain. I wanted not to host my blog at root of my github account `nsaikiran.github.io`
because if I want to setup project pages for my projects. I don't like the links to that.
So, I created a repository for my blog. And pushed all the code to a specially named branch called `gh-pages` .
I can access my blog from `nsaikiran.github.io/blog`. 

It is easy to host a website in user/organization page.Here I'm using github project pages to host my blog.

 

While mentioning your `url` in `_config.yml` file. The `url` must be `*protocol://*www.domain.topleveldomain`
 or `protocol://domain.topleveldomain`. Because whenever we use `site.url` to generate links, if we didn't 
 mention the protocol, it will be considered as relative path.
 
 

[Link to Github Pages]: https://pages.github.com/
