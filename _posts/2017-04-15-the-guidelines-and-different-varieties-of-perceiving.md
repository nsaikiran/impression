---
layout: post
title:  "The guidelines and different varieties of perceiving"
description: "Understanding data types and configuration files"
categories: ["cs"]
author: "Sai Kiran"
---

*This post is the result of my attempt to better understand software systems. 
And this is just an inception.* 

## Guidelines

Answers to all these questions have something in common:
- Why do we experience any sort of errors during software production or execution?
- Why should we write configuration files in a particular way? 
- Why the frameworks(that are born to assist the software development) influence our style of programming?  

Let us consider that you want to accomplish something, 
Knowing 'clearly' what you wanted. 
And you know who can help.
Then you need to know how to communicate your need.  
The crucial part is how you are going to communicate your need.  

If it is a computer that you are trying to communicate with, 
you are expected to follow some *guidelines* to be understood properly.
Those *guidelines* are everything for computers. 
So those guidelines need to be properly designed, understood and used.

All of the software that I know has concrete `guidelines` to communicate with them.
> And we are expected to follow the `guidelines`.

So, all the of the answers to the above questions have *guidelines* in common.

## Different varieties of perceiving
And now we'll try to answer below questions.
- How the data is interpreted? 
- How come we have these many varieties of *data* and *file* types.

What can be understood by looking at the extension of the file is that it defines 
how to generate such a file and read it. 
A video/audio file can't be opened by a text editor.
Because the text editor is designed to understand and generate a *plain text* file.
And the VLC media player can be used to generate and play *media* files. **File Formats** 
is the magic. We use **file format** specification to generate and read files.
That is the reason for every file format we have a different software. 

> The file format specification is a happy handshake between encoder and decoder.

We have different file formats for different types of files like text, video, image etc.
Or same type of file with some added guidelines like `.html`, `.py` etc.

The file format specification is the *guidelines* here. 
But the point I'm trying to make here is that even though 
the data is stored in bits, it is perceived *differently*.

For example most of the programs expect `arguements` in string format. 
Those arguments are stored in an understood location. In the program we 
take those arguments and even change the type of data in those arguments 
to accommodate required operations. We have many examples for this.