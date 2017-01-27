---
layout: post
title:  "How did I understand web page?"
date:   2017-01-27
categories: ["tech"]
author: "Sai Kiran"
---

That was really fun viewing my own image, using *marquee* and *blink* tags with both text and images 
in a web page, during the early days of college education.

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
interaction. It was intended for tasks, for which Java was too heavy.
Check out [Virtual Machines, JavaScript and Assembler][Scott Hanselman, "Virtual Machines, JavaScript and Assembler" - Fluent 2014 Keynote], 
for some more information on *birth* of JavaScript. [The Birth & Death of JavaScript][]  will give 
you lot more other details. [Wat][] will introduce you to few bad parts of JavaScript.

> I feel CSS and JavaScript are part of HTML but separated for a reason. 


### How we write

HTML is just like manuscript markup.
We take plain text and mark it up with HTML for its styles, layout and dynamic behavior. 

When you specify a piece of text to be a Heading, you don't know *how* that is implemented. In the 
same way to make CSS and JavaScript work, just link the code &mdash; don't write in HTML file.

> Remember that without a HTML tag, there is no way you can add CSS or JavaScript.

### How browsers render

Browsers will be using Document Object Model ([DOM][]), and CSS Object Model ([CSSOM][]) 
to [render][Page rendering] the pages. We can change those object models using JavaScript to make 
the user feel "Owwww....!".    

All topics in [Web Fundamentals][] will help you develop better web applications keeping 
performance in mind.

Few more resources: [Web Style Sheets](https://www.w3.org/Style/), [Blink tag](https://www.w3.org/Style/customdtd), [History of CSS](https://www.w3.org/Style/LieBos2e/history/Overview.html)


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
[Wat]: https://www.destroyallsoftware.com/talks/wat
[The Birth & Death of JavaScript]: https://www.destroyallsoftware.com/talks/the-birth-and-death-of-javascript

<!--Webpage is marked up using tags-->

<!--You specify `what` in HTML and `how` in CSS and JavaScript, depending on the what you are -->
<!--trying to do: styling and layout, or behavior. Sometimes we tend to write CSS and/or JavaScript in HTML file.--> 
<!--It seems OK &mdash; but not. Because rather than *what* you are specifying *how*. -->
<!--Then, the file will be clumsy with *what* and *how*.-->