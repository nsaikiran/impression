---
layout: post
title:  "Significance of extern and static keywords in C"
categories: ["cs"]
author: "Sai Kiran"
---

Consider a module in a C program. 
When I say a module ,it can be a piece of large project. 
Let us call it as a translation unit. 
Because modular programming helps the programmers working on a large project. 
To understand keywords `static` and `extern` , we need to understand *linkage* and *storage class*es in C. 
Most of the times description of the above keywords confuse. 
## Storage Classes
There are two types of storage classes (describes the life time of the variable) in C. 

Those are

1. automatic storage class
2. static storage class

> A variable with automatic storage class will have its lifetime equal to the execution time of the block it is defined in.

> A variable with static storage will have its lifetime equal the execution time of the program (The variable can retain its value between function calls) .

We can divide any translation unit into two parts.

1. internal to a function
2. external to all functions

You can find global definitions/declarations (not every external declaration/definition is global because of scope ) and preprocessor directives (most often) external to all function. 
Of course you can have preprocessor directives anywhere in the translation unit.


According to the standard all the variables defined external to all functions will have static storage class (It has nothing to do with static keyword).

> If you want to define a variable internal to any function with *static storage class* then you need to use `static` keyword.

## Linkage
Linkage determines whether the same name in another scope refers to the same object or function. You can have two types of linkages. Those are

1. internal linkage
2. external linkage
3. no linkage

We use internal linkage only for translation unit. 
You may want to hide some of global variables or function definitions (global means external to all functions ) 
from other translation units, in that case you can specify internal linkage using `static` keyword. Hence, internally linked variables/functions can't be accessed from other translation units.

We generally use *external linkage* for communication among translation units. 
We can allow all translation units to use the same definition of a function/variable. 
Unless you use `static` keyword with functions/variables defined external to all functions, 
they will have external linkage, hence can be 
called/accessed from any translation unit, provided that the translation unit knows the declarations of the 
functions/variables (may be using header file). 
What if you want to use the same definition of a variable in all translation units. 
We know that we can have any number of declarations of a function/variable but only one definition. 
Functions have prototypes to declare (no definition). 
*How can you actually declare a variable?*.
Here is the way (only way) of declaring a variable in C, i.e, by using `extern` keyword. 
This tells the compiler that the identifier has been defined somewhere (and resolve its location during linking) but I will access here.

A block-scope variable defined without `extern` will have no linkage.

If the definition of the external variable occurs in the translation unit before its use in a particular function, 
then there is no need for an *extern declaration* in the function. Because of this reason we are able to access global variables in functions.

## Specifying *storage class* & linkage
Some keywords are used for syntactic convenience in C. That confuses a lot.

We use *storage-class* specifiers (some keywords) to specify the storage properties of a variable, 
those are `auto`,`register`,`static`,`extern` and `typedef` .

Don't think all these keywords will specify storage class (either automatic or static).

- **auto** - announces variable has automatic storage-class.
- **register** - announces variable has automatic storage-class (if possible store it in CPU registers)
- **static** - It has two roles.
    1. Specify `static-storage` class for internally defined variables.
    2. Announce internal linkage for an identifier (function/variable) defined external to all functions.

- **extern**  - It specifies that this identifier has been defined somewhere(external) hence no need to allocate memory
    1. If you want to use function defined in somewhere we need to use
          `extern ret-type func(type arg,...);`
         But it is same as   `ret-type   func(type    arg,...);`.
         Hence it is optional to use `extern` with declaration of identifier for a function
    2. For variable identifiers : 
        If you want to use variables defined in some other scope 
        (like other translation units) you need to specify:
         `extern type var-name`

- **typedef** - does not reserve storage and is called a storage-class specifier only for
syntactic convenience.

-------

## Bookmarks

### References
- *The C Programming Language 2nd Ed* by Brian Kernighan and Dennis Ritchie

### Code Examples
- [Heap Sort Implementation](https://github.com/nsaikiran/MyPrograms/tree/master/C/HeapSort)

### Others
- [Heapsort program in C](http://myprogramsforyou.blogspot.in/2015/08/heapsort-program-in-c.html)