---
layout: post
title:  "How I setup this blog"
categories: ["tech"]
author: "Sai Kiran"
---

I bought `saikiran.blog` for my personal blog. I heard about Github pages,
Hosting a blog is possible because of [Github Pages][Link to Github Pages].
First I bought a `.blog` domain. I wanted not to host my blog at root of my github account `nsaikiran.github.io`
because if I want to setup project pages for my projects. I don't like the links to that.
So, I created a repository for my blog. And pushed all the code to a specially named branch called `gh-pages` .
I can access my blog from `nsaikiran.github.io/blog`. 

It is easy to host a website in user/organization page.Here I'm using github project pages to host my blog.

 

While mentioning your `url` in `_config.yml` file. The `url` must be `*protocol://*www.domain.topleveldomain`
 or `protocol://domain.topleveldomain`. Because whenever we use `site.url` to generate links, if we didn't 
 mention the protocol, it will be considered as relative path.
 
 
While checkig the site locally using `jekyll serve` commmand, site.url will be localhost:4000 and 
other values like site.baseurl will be read from _config.yml.
 
 site.url
 site.baseurl
 
 Github begin:
 `site.github.url` will set if the website is hosted in `Github`. And that will be the `full` path
 of repository. Ex: (If the website is hoted in user/organization page, it will be username.github.io.
 If it is a project page it will be `username.github.io/project`. We can use this while generating the 
  urls.
  
  And
   site.url in _config.yml will be overriden to username.github.io
   site.baseurl in _config.yml will be overriden to /project or "". based on whether the site is hosted
   in user page or project page.
End

If the site has a custom domain name,

site.url = site.github.url = custom domain.

site.url will be set to that custom domain name
site.baseurl will be considered from _config.yml. Don't set it. 
In my case I'm using custom domain (`saikiran.blog`)

[Link to Github Pages]: https://pages.github.com/
