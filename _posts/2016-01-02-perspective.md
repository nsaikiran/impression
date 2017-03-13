---
layout: post
title:  "A different perspective of contemporary programming"
date:   2016-01-02 19:45:31 +0530
categories: ["tech", "cs", "impression"]
author: "Sai Kiran"
---

Nowadays, *programming* is not that hard as it was earlier. Moreover, a
programmer need not have a *formal background* in programming, though, it
often depends on the problem.
We can classify the problems broadly as End User Applications, Systems
Programs, and Infrastructural Software etc. 


High level constructs, efficient libraries, proper standardization are
some of the reasons why programming in most of the cases [seems simple][xrds-link].
Sometimes it seems to me *whether we really are programming a computer or
not?*  We are not *directly* giving instructions to a computer, we are
instructing the high level constructs available, with languages.  Those
constructs -`printf`, `scanf` etc. to name a few - hide most or almost all
of the complexity and instruct the computer (generating instructions
that are in one to one correspondence with computer's instructions set).
But this process is not as easy as it seems.  We have to pass through
many of such constructs. For example, one construct may use another and
so on. These transform our high level - often very high level - source
code to computer instructions: compiler/interpreter, pre-defined
libraries, standard libraries, system calls and assembler.  


As end programmers, we are enjoying the compiler technology that
features us with high level constructs. If you are a Python programmer,
you can use those easy to use data-types it provides with a single
Python instruction. 
Like

~~~ python
data = list()    
data.append("hello")
data.append(23)
~~~
We should not think these are to be understood by the computer (bare
machine). These are understood by intermediate systems and they modify
them such that the computer can understand. We are just programming
(instructing) the constructs, intermediate systems. My intention is not
that one has to go for low-level programming but as mentioned, it is a
**different perspective of modern programming**. 


If you want to enjoy knowing the difficulties in building those
constructs, you can revolutionize.

[xrds-link]:  http://xrds.acm.org/blog/2014/07/programming-computer-science/
