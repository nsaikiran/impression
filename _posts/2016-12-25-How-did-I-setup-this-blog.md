---
layout: post
title:  "How did I setup this blog?"
categories: ["tech"]
author: "Sai Kiran"
---

## Host the site
I heard about [Github pages][Link to Github Pages], and [Jekyll][Link to Jekyll] and came to know that Github pages are powered by Jekyll.
So, I wanted to host my blog in Github using Jekyll.

After understanding Github pages structure, I wanted to host my blog as project site, not as user site.
Because, If I set up my blog as user site, then `http://saikiran.blog` should point to`https://nsaikiran.github.io`. 
Suppose If I want to have a page for any of my repositories, then that (`https://nsaikiran.github.io/*repository*`) will live at  `http://saikiran.blog/*repository*`,  which I didn't like. 

Then I chose a Jekyll theme, installed [Jekyll][Jekyll installatin] and theme specific gems to run locally before pushing it to Github. 
I created a [repository][blog-repo] for my blog. And pushed all the code to a specially named branch called `gh-pages` . 
Now I can access my blog from `https://nsaikiran.github.io/blog`.

### Useful references
* [Jekyll doc][Link to Jekyll doc]
* [Clarification about site.baseurl][Link to url clarification]. 
* [Configuring Jekyll for User and Project GitHub Pages][Configuring Jekyll for User and Project GitHub Pages]
* [Absolute vs. Relative Paths/Links][Absolute vs. Relative Paths/Links].

The above links helped me setting up the site properly as well as customizing it.
I'm new to Jekyll and using Github project site.
There was an issue with generating URLs. Because my blog doesn't live at [root][root],
rather it will be in [sub-directory][code-base] of root. 
In `_config.yml`, we can set `url` and `baseurl` with the other variables. 
We use these variables to generate URLs/links, so these should be configured properly. 

And sometimes using `baseurl` might drive you crazy. 
If you want to avoid the confusion around using `baseurl`. 
Unset the `baseurl` and `site.url`.
While generating links, instead of `site.url`, use `site.github.url` which will be set to `https://*your-account*.github.io/*repository-name*` while in Github environment. 
For more information refer [Project Page URL Structure][Project Page URL Structure].
<!--You can check your site locally with `jekyll serve`.-->

## Setup custom domain

Bought a domain name under recently released  top-level domain `.blog`.
Steps:  
* [Configuring a GoDaddy domain name with GitHub pages][Configuring a GoDaddy domain name with GitHub pages].  
* If you used `site.github.url` in link generation, you no need to do anything.  
* If you used `url` and `baseurl` in link generation, set`url` to the custom domain, in my case `http://saikiran.blog`
and unset `baseurl`  

You have your site up and running. 
Now you can maintain the source code of your site like any other project codebase.

[Link to Github Pages]: https://pages.github.com/
[Link to Jekyll]: https://jekyllrb.com/
[Link to url clarification]: https://byparker.com/blog/2014/clearing-up-confusion-around-baseurl/
[Link to Jekyll doc]: https://jekyllrb.com/docs/home/
[Project Page URL Structure]: https://jekyllrb.com/docs/github-pages/#project-page-url-structure
[Configuring Jekyll for User and Project GitHub Pages]: http://downtothewire.io/2015/08/15/configuring-jekyll-for-user-and-project-github-pages/
[Absolute vs. Relative Paths/Links]: http://www.coffeecup.com/help/articles/absolute-vs-relative-pathslinks/
[Configuring a GoDaddy domain name with GitHub pages]: http://mycyberuniverse.com/web/configuring-a-godaddy-domain-name-with-github-pages.html
[blog-repo]: https://github.com/nsaikiran/blog
[code-base]: https://nsaikiran.github.io/blog
[root]: https://nsaikiran.github.io
[Jekyll installatin]: https://jekyllrb.com/docs/installation/


<!--Now-->
<!--If you are hosting your blog as user site then -->
<!--url = https://nsaikiran.github.io-->
<!--baseurl = ""-->

<!--If you are hosting your blog as project site then -->
<!--url = https://nsaikiran.github.io-->
<!--baseurl = "/blog"-->

<!--Use site.url and site.baseurl while generating links. So that you can configure links from -->
<!--Hosting a blog is possible because of [Github Pages][Link to Github Pages].-->
<!--First I bought a `.blog` domain. I wanted not to host my blog at root of my github account `nsaikiran.github.io`-->
<!--because if I want to setup project pages for my projects. I don't like the links to that.-->
<!--So, I created a repository for my blog. And pushed all the code to a specially named branch called `gh-pages` .-->
<!--I can access my blog from `nsaikiran.github.io/blog`. -->

<!--It is easy to host a website in user/organization page.Here I'm using github project pages to host my blog.-->

 <!---->

<!--While mentioning your `url` in `_config.yml` file. The `url` must be `*protocol://*www.domain.topleveldomain`-->
 <!--or `protocol://domain.topleveldomain`. Because whenever we use `site.url` to generate links, if we didn't -->
 <!--mention the protocol, it will be considered as relative path.-->
 <!---->
 <!---->
<!--While checkig the site locally using `jekyll serve` commmand, site.url will be localhost:4000 and -->
<!--other values like site.baseurl will be read from _config.yml.-->
 <!---->
 <!--site.url-->
 <!--site.baseurl-->
 <!---->
 <!--Github begin:-->
 <!--`site.github.url` will set if the website is hosted in `Github`. And that will be the `full` path-->
 <!--of repository. Ex: (If the website is hoted in user/organization page, it will be username.github.io.-->
 <!--If it is a project page it will be `username.github.io/project`. We can use this while generating the -->
  <!--urls.-->
  <!---->
  <!--And-->
   <!--site.url in _config.yml will be overriden to username.github.io-->
   <!--site.baseurl in _config.yml will be overriden to /project or "". based on whether the site is hosted-->
   <!--in user page or project page.-->
<!--End-->

<!--If the site has a custom domain name,-->

<!--site.url = site.github.url = custom domain.-->

<!--site.url will be set to that custom domain name-->
<!--site.baseurl will be considered from _config.yml. Don't set it. -->
<!--In my case I'm using custom domain (`saikiran.blog`)-->


<!-------------------->

<!--So decided to have my blog as project page. In my case `https://nsaikiran.github.io/blog`. -->
<!--I used `http://saikiran.blog` for `https://nsaikiran.github.io/blog` .-->


<!--I can host my blog as user site or project site. All the sites (user sites and project sites) associated -->
<!--with a user or organization are served from a special url tied to user/organization. It looks like -->
<!--`https://*your-account*.github.io` where *your-account* is replaced with username of gihthub.-->

<!--So, user/organization site will be `https://*your-account*.github.io` . And project sites will be -->
 <!---->
<!--`https://*your-account*.github.io/*repository-name*` where *repository-name* is replaced with project's repository name.-->

<!--In case of user/organization site the site's code will live in `master` branch of special repository with name `your-account*.github.io` . -->
<!--For project sites, the site's code will live in special branch named `gh-pages` of the project repository.-->

<!-------------------->