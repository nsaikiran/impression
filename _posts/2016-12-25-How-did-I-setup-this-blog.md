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
* If you used `url` and `baseurl` in link generation, set`url` to the custom domain, in my case `http://saikiran.blog` and unset `baseurl`  

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