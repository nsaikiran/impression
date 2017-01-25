---
layout: post
title:  "How did I understand the web?"
categories: ["tech"]
author: "Sai Kiran"
---

----------------

Webpage is marked up using tags

-----------------
That was really fun viewing my own image, using *marquee* and *blink* tags with text and images 
in a web page during the early days of college education.

But few years later, in my undergraduate course, I was trying to understand &mdash; 
how we write web pages and &mdash; how browsers render them.

It seemed I have to learn HTML, [CSS][] and JavaScript &mdash; 3 different 
languages, to create a web page. What? I didn't know that. So, wanted to 
figure out *why*.

When we describe **HTML** &mdash; *[Hypertext][] [Markup][] Language*, it 
seemed it can alone define a webpage &mdash; including elements, styles and 
in my opinion &mdash; dynamic behavior as well.

So, why should we learn three different languages. Finally I found the answer 
here at [Web Standards][] &mdash; And it says `They’re simply an evolution of the web`.

So, let us see how they evolved.

We have HTML, CSS and JavaScript &mdash; the building blocks of 
the World Wide Web, to create stylish and interactive webpages.

First came HTML, then CSS was born by seperation of layout and style information from the HTML.


JavaScript was born to provide interactivity to the web pages. It is mainly used for 
DOM manipulations &mdash; Changing web page's content, style and layout based on user's 
interaction. It was intended for tasks for which Java was too heavy.

Check out [Scott Hanselman, "Virtual Machines, JavaScript and Assembler" - Fluent 2014 Keynote][]

> I feel CSS and JavaScript are part of HTML but separated for a reason. 


### How we write

HTML is just like manuscript markup.

We take plain text and mark it up with HTML for its styles, layout and dynamic behavior. 

When you specify a piece of text to be a Heading, you don't know *how* that is implemented. In the 
same way to make CSS and JavaScript work, just link the code &mdash; don't write in HTML file.


Sometimes we tend to write CSS and/or JavaScript in HTML file. It seems OK but not. 
Because then rather than *what* you are writing *how*. Then the file will be clumsy with 
*what* and *how*.

> Remember that without a HTML tag, there is no way you can add CSS or JavaScript.

You specify `what` in HTML and `how` in CSS and JavaScript, depending on the what you are 
trying to do: styling and layout, or behavior.


> [DOM][] is the actual representation of webpage in memory. 

### How browsers render

Browsers will be using Document Object Model ([DOM][]), and CSS Object Model ([CSSOM][]) 
to [render][Page rendering] the pages. We can change those object models using JavaScript to make 
the user feel "Owwww....!". DOM is created from HTML    

That is the reason they are separated.


**Demo** can be created.
> 1. Take a plain text
> 2. Markup that with HTML.

All topics in [Web Fundamentals][] will help you develop better web applications keeping 
performance in mind.

Reference:

[Web Style Sheets](https://www.w3.org/Style/)

[Blink tag](https://www.w3.org/Style/customdtd)

[History of CSS](https://www.w3.org/Style/LieBos2e/history/Overview.html)


[Hypertext]: https://www.w3.org/WhatIs.html
[Markup]: https://en.wikipedia.org/wiki/Markup_language#Etymology_and_origin
[Web Standards]: https://www.w3.org/wiki/The_web_standards_model_-_HTML_CSS_and_JavaScript
[CSS]: https://www.w3.org/Style/LieBos2e/history/Overview.html
[CSS Timeline]: https://www.w3.org/Style/CSS20/
[CSS History]: https://www.w3.org/Style/CSS20/history.html

[DOM]: https://www.w3.org/TR/DOM-Level-2-Core/introduction.html
[CSSOM]: https://varvy.com/performance/cssom.html
[Page rendering]: https://developers.google.com/web/fundamentals/performance/critical-rendering-path/render-tree-construction
[Scott Hanselman, "Virtual Machines, JavaScript and Assembler" - Fluent 2014 Keynote]: https://www.youtube.com/watch?v=UzyoT4DziQ4&feature=youtu.be
[Web Fundamentals]: https://developers.google.com/web/fundamentals/

-------------------------------

[Web Fundamentals][]: To understand everything related to Web development.


But after sometime I was starting to work with web. Understanding how web 
pages are created. 

 HTML is used to build the skeleton. CSS is used to position and color the 
 components of the page. Finally, JavaScript is used for DOM manipulations 
 (It was intended for tasks for which Java was too heavy).

 So I referred definitions. Then I felt there should not be 3 different 
 languages because the acronym HTML -- Hypertext Markup Language, according 
 to its name it should have features of CSS and JavaScript as well. *Because we are using CSS and JavaScript for **Markup***
 
 
 The evolution of these technologies is different.
Componets of web: HTML CSS Javascript.

First I wanted to have a clear idea of what is HTML and what is not.
Clear separation of these technologies. I don't know why I wanted to do that. But I wanted. And I started
then with structure and styles and layout. Then Styles and layout 
were separated in to CSS.