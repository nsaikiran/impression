---
layout: post
title:  "Server side vs client side rendering"
description: "server side vs client side rendering"
categories: ["server-client"]
date: 07-03-2024
author: "Sai Kiran"
---
## Introduction
> What is server side vs client side rendering?

Here, rendering mean, "generation" of HTML page that is final. Server side rendering mean that the webpage is generated at server side and that is sent to client (browser) for rendering. Client side rendering mean, a basic HTML page with "heavy" javascript code that generates the full HTML page from the basic HTML page that is returned.
There are differences between those. Each one has its own pros and cons. We need to select the one that is appropriate for us in our solution's context.

## Learnings
1. Client side rendering: REST APIs are exposed through service, at client side, javascript will generate(or render) HTML page and then "visually rendered by the browser". Libraries like React is used in this setup.
2. Server side rendering: The service will return a fully constructed HTML page (of course javascript files will be required to define various actions and modifications to the HTML document). This HTML page is constructed at server side. Applications will use templates to generate the response.
3. Static site generation, is a server side rendering of pages, so that there won't be dynamic process required to generate the response.

This is a rough notes to record my learnings.

![Image that explains server-side, client-side rendering and static side generation]({{'/assets/images/sys-design-the-web/slide.jpg' | absolute_url }})
This is taken from [ AWS re:Invent 2023 - Scaling on AWS for the first 10 million users (ARC206) ](https://www.youtube.com/watch?v=JzuNJ8OUht0&t=2188s) refer slides at [slideshare](https://www.slideshare.net/search?searchfrom=header&q=+Scaling+on+AWS+for+the+First+10+Million+Users+&page=2) for 2023 AWS event.

## Footnotes
### Server-side rendering
![Server-side rendering](https://miro.medium.com/v2/resize:fit:1400/format:webp/1*CgrMqqxMCltl4BVjGgFRKA.png)
Refer [What is the Server-Side Rendering and how it works](https://web.archive.org/web/20230906083637/https://ferie.medium.com/what-is-the-server-side-rendering-and-how-it-works-f1d4bf9322c6)

### Client-side rendering
![Client-side rendering](https://miro.medium.com/v2/resize:fit:1400/format:webp/1*kwlw0Y8ZYd3-YbW0WuFR7w.png)
Refer [What is the Client-Side Rendering and how it works](https://web.archive.org/web/20230523142405/https://ferie.medium.com/what-is-the-client-side-rendering-and-how-it-works-c90210e2cd14)

### Static-site generation
Example of server-side rendering.