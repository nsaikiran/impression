---
layout: plain
title:  "**Fundamentals of datastructures"
description: "fundamentals of data strucures"
categories: ["cs"]
tags: ["execution-models"]
author: "Sai Kiran"
---

This post depicts the how I tried to achieve "connected" understanding of datastructures. You are assumed to have some basic knowledge on standrad DS. 
To understand computers we need to understand the memory, an important component.
The memory or main-memory is where computer stores data under process. CPU fetches/store the data from/to memory as it works. So, obviously how fast we are able to fetch/store the data will affect the overall time to finish certain operation on the data. Hence, data structues is organizing the data in memory for efficient retrieval/storing.

To better organize the data we need to understand how memory looks like, we may need to compare various data structures based on the constraints/requirements etc. 
Memory is a gaint array of byes. 
We compare various DS on the basis of time they take to finish certain operations. Because we always want to minimize the time taken.
To compare various DS we need a theoretical computer, on which we calculate time each operation takes. 
Why a theoritical omputer? Because we've computers with various hardware configuration like computers with more clock speed, more/less RAM, various levels of cache, these days we've multi-core processors. So, to simplify the analysis, to make a common ground for benchmarking we choose a theoritical model, RAM model of computation.
So, with RAM model, we are avoiding the influence of hardware config on analysis. 


# RAM

simpliefied computer: single procesor, no cache, each basic insttuction take constant time.
Get to know more about RAM [here](https://www8.cs.umu.se/kurser/TDBA77/VT06/algorithms/BOOK/BOOK/NODE12.HTM#SECTION02131000000000000000) and [here](https://www.cse.cuhk.edu.hk/~taoyf/course/comp3506/lec/ram.pdf).

But I'm also listing provoerties here:

- Each simple operation (+, *, -, =, if, call) takes exactly 1 time step.
- Loops and subroutines are not considered simple operations. Instead, they are the composition of many single-step operations. It makes no sense for ``sort'' to be asingle-step operation, since sorting 1,000,000 items will take much longer than sorting 10 items. The time it takes to run through a loop or execute a subprogramdepends upon the number of loop iterations or the specific nature of the subprogram.  
- Each memory access takes exactly one time step, and we have as much memory as we need. The RAM model takes no notice of whether an item is in cache or on the disk, which simplifies the analysis. 


# Accounting
## Accounting on RAM
we alwasy take a relative decision. We choose an Algo/DS which is relatively better than the one we had. So, alwasys comeup with as mamay Also/DS as yo ucan and relatively choose whichever is better on RAM.
For a particular DS/Algo, we generally need the time it takes to finish an operation and how much actual memory our DS takes (in reality memory is also a scarse resource like time) to compare it with other DS/Algo. So, as we are using RAM as our only computer on which we benchmark everything, the only factor that affects the runtime of algorithm is size of the datastruture/size of data incase of algorithms. For example, to fetch the last element on linked list with 10 elements will take us 10 memory accesse, if the size if 5 then 5. etc.
So, the time complexity is functino of input.

## asymptotic 
As computers are operating more and more on large amounts of data we use what is called as asysmptocic analysis while comparing two algo/DS. So, after formulating the the time compleity, we then simplify it assuming that the input is very large, (close to infy). This will further simplify our analysis.

(
The running time is a function. It is a funciton of input.
By choosing RAM model we've removed the machine specifics from the analysis (analysis to choose the best DS), this is the first major step in analysis.
And we are also intersted in the runtime when the input is very large, we call this asymptotic analysis. Because it gives us the worst-case running time.
So, we produce worst-case running-time function, best-case running-time funciton and average-case running time function after the analysis. Thought most of the time we are interested in worst-case running-time function.
As it is a theoretical model and we cover a problem not a specific instalce of the proglem. We mention time and space needed to finish operation in function of input. 
For example accessing memory takes a unit time. If we needed to do 10 such operations to finish an operation. Genrelizing it makes O(n) - descibe it.
Mention asysmptotic analysis and give links here.
https://www.cs.cmu.edu/~clo/www/CMU/DataStructures/Lessons//lesson9_1.htm

How are we gonna compare the data structures? by runn
To do that we need a theoretical model
)


## Organizing data on memory
We know memroy is a gaint array of bytes. For the east of discussion, let us define, group of bytes to be an object and group of objects to be DS.



# Introduction
This is hyper-linked notes I took for DS.
Computers operates on data. By studying various DS, their strenghs and drawbacks helps us 
The generic idea of computer is that it (takes in some data and )operates on data. 
And to operate on data it takes certtain amount of time. When learning data structures our goal is to keep the time spent reasonable.
After all, we don't want to stare at screen till the problem is solved.

Computers have memory to store data under opration. ie. main memory. How we organize data in memory affects the time to finish certain operation. 
Hence we explore how to better organize the data in memory.

We always ideate on different datastructures that provide a specific operation. And analyse the time each DS takes, and by comparing those we decide on the best DS and pick that. Hence the analysis is importatnt.

# RAM
As there are many varieties of computers produced by various vendors, and have different capabilities. But we want our prolesm to be solved by all of them.
For that we want to pick a better DS or algorithm. 
Faster computers will be faster, than the ones which have less computing resources. But the analysis we do is regardless of the harware. Hence we should reason the the time/space complexity independent of the machine specifics, memory hierarichies, no. of processors, amount of memory, processor speed etc.
If we choose a better algorithm it will be better for any machine. As there are many varieties of computers, we don't consider the specifics of computers in reasoning about time to finish operations.
Hence, to make our analysis indepedent of machine,
To explore this we use a need simple (abstract)model of computer probably therotical one. We take RAM model of computer.
Get to know more about RAM [here](https://www8.cs.umu.se/kurser/TDBA77/VT06/algorithms/BOOK/BOOK/NODE12.HTM#SECTION02131000000000000000) and [here](https://www.cse.cuhk.edu.hk/~taoyf/course/comp3506/lec/ram.pdf).

But I'm also listing provoerties here:

- Each simple operation (+, *, -, =, if, call) takes exactly 1 time step.
- Loops and subroutines are not considered simple operations. Instead, they are the composition of many single-step operations. It makes no sense for ``sort'' to be asingle-step operation, since sorting 1,000,000 items will take much longer than sorting 10 items. The time it takes to run through a loop or execute a subprogramdepends upon the number of loop iterations or the specific nature of the subprogram.  
- Each memory access takes exactly one time step, and we have as much memory as we need. The RAM model takes no notice of whether an item is in cache or on the disk, which simplifies the analysis.   

Because RAM should only read data from Ram memenory, and computations done in registers is constant. Hence we are more focused on accessing data from ram memory.
As descibed above RAM has memroy in which data is stored. 
- The memroy is byte addressible. It has indexes sarting from 0. We can access any byte with its index
- Each byte can be accessded independtly.
- Accessing anybyte takes a same amount time.
- index of a byte can be stored in another 


RAM takes some time to finish the operation. Our goal is to minimize the time. The way data is organized affects the time it takes to finish.

Pointer is an address of a byte. We point to first byte of the record usually. To go to next object, we jump to address of first byte of the next record. 
We do this by adding the current pointer with no. of byte current occupies.

## Accounting on RAM
The running time is a function. It is a funciton of input.
By choosing RAM model we've removed the machine specifics from the analysis (analysis to choose the best DS), this is the first major step in analysis.
And we are also intersted in the runtime when the input is very large, we call this asymptotic analysis. Because it gives us the worst-case running time.
So, we produce worst-case running-time function, best-case running-time funciton and average-case running time function after the analysis. Thought most of the time we are interested in worst-case running-time function.
As it is a theoretical model and we cover a problem not a specific instalce of the proglem. We mention time and space needed to finish operation in function of input. 
For example accessing memory takes a unit time. If we needed to do 10 such operations to finish an operation. Genrelizing it makes O(n) - descibe it.
Mention asysmptotic analysis and give links here.
https://www.cs.cmu.edu/~clo/www/CMU/DataStructures/Lessons//lesson9_1.htm

## Organizing data on memory
Data is organized in memory.
How we organize the data affects the time it takes to finish certain operations.
Assume we are working at at time with on ly one problem. 
The data is related to a bpoblem.
As we use memory of RAM to store data under operaton, we read and write the to the memory. 
For the sake of ease of explaning, I'll consider data under operaion to be group of objects.
Data strcture is group of objects with a specific way to traversing them.

Each reacord/object is the basic element of data structure.

Hence the basic operations will be be adding more objects, deleting existing objects, modify existing ones and finding objects with required attributes.
For now assume all records in DS are of same type and has same size.

We explore the well known data structures.
### linear/contigous
Lets explore organizin data under processing in RAM and check the time to take all basic operations:
The first way to organize the data is storing records linear/consecutive. Here, every element is stored next to its previsou element.

While traversing the DS, may be to find an object with a specific key, we jump to the next object, until we read end of DS or we found our target object.
Another advantage here, is if you want to access nth element the next address to jump can be calculated. And the nth element can be accessed in constant time.
But what about delete? Deleting someting in middle destroys the assumption that the next element can be found just beside.
You can easly insert at the end. finiding takes O(n) time.
https://www.cs.cmu.edu/~clo/www/CMU/DataStructures/
Array is traversed linearly and data is organized in memory contigously.
So, if you are storing the data contigously, then you need to specify the max. amount of size, as we need to check for that much of contigous memeory. We need to reserve tat much of memory.
### non-linear/linked
To facilitate the deletion, we can need to use another way of organzing data, a non-linear/non-contigous ways.
Where each record will store the address of next record. Linked list. single/double. your wish.
But here we loose the benefit of accessing nth element in constant time.

See, find/seach are such an importatnt operation as it may be subproblem of every operation.
Hence we try to optimize.
Linked lists are traversed lineraly and stored non-contigously.

#### trees
https://www.cs.cmu.edu/~clo/www/CMU/DataStructures/
If you traverse the DS linearly, then we may call it linaer DS. Ex: array, LL, and ADTs constructed with these. Find/search will be of linear in the size of input.
Hence tree is an example of non-linear DS.
Considering our goal of reducing time, we are more interested in a DS like BBST. Where you'll have find/search operation in logarithmic of input. 
In this DS we store 
We may be storing he elements the order we received into linear structure and finding an element in that is of linear tiem.


But if we were to arrange data in such a way that the find operation we want will be fast.
Hence we need to rearrage the items/ or create a specific DS that helps to achie our goal. One such example is BBST or height balanced BST.
First we understand BST. every node has two children right childre in greater and left children is lesser than the key.
By this, the key under seach is greater you make a right move, with this you've reduced your search space to only the right subtree of the no de.

When the height is balanced, every steap we take we are reducing the searchs pace by half. Which is similar to binary search.

We shoud make sure that before and after any operation that alters the DS, the DS is in which it caters the initial need. For example to get the 
benefit we need the BST to be always balanced. so, we will spend time to make it balance every time we didi a operation.

Reference: https://www.cs.cmu.edu/~clo/www/CMU/DataStructures/Lessons//lesson4_1.htm

More generilized structres are also there.
B trees, B+ trees that has wide usage in the databaeses.

DS is the way we traverse the DS. We now see trees, wheere every record has two hildren, wile traverse sing we choose a child. This is similar to binary seach. Wheere it reduces search space by half on each choince.
So, it gives us logarthmic complexity.
But they must be balance to ge the benefit everytime. Hence we make sure after every operation like insert or delete we make sure it is balanced.
There are many variants of tree. binary trees is an example.


As we discussed fundametal DSs. linear (array, linked list) and non-linear (trees)
linked list and array are different, as the items are stored non-linearly but accessed lineary in linked list.

As the computers we use are general purpose computers, more than ope progrems's data is stored in data. 
Hence, we alsys need to be deterministic aobu the size of linear block we need. So that those many consecutive blocks can be serached for and allocated. Hence for creating a array of objects we need to specif t the size of array upfromn.t
But the linked lists are nonlinear stored hence space. the items are not stored consecutivley hence we don't need to mention the size.

## Furthur Reading on DS:
Watch an interesting talk on DS by Sean Parent: https://www.youtube.com/watch?v=sWgDk-o-6ZE. Here he explains deriving various possible relationships on the data we are working with and using those relation ships to construct better performing DS for our specific usecase.

# Abstract Data tyes:
The objects with their operations is type. values and operations on those values are data types.
ADT. Where implemenation is not mentioend. 
Stack, Queue, Circuar queue, Priority queue, graph. min-max-heap, heap, hash map, hash table, hash set, dict, dynamic array.

Note: (afer list is discussed in RAM)
In general purpose computers, where, you have memroy limited and more than one DS lives in the memory (more thatn one problem may be solved).
So, probmising a contilous blocks is little tricky. So, we mention maximum size we want, so that only that much is allocted for us.


# DS in programming languages

many high level programm alngauges are providing lot of datastructures as buildtin. For example in pytion, js, we dont need to implement ds. For jaba and C+= u get eveuting in stadn librau.
these lnagues are moreinteresting as to how they define the builtin types. for example pyton has dict, list as builtin tpes.  these are very generic dta strucres though.
any tupe of data can be stored, even then we get the enefit of ds.

list is dynamic array. used talble doubling to achive this. the idea of containers. the container that can grow/ adjust its size by not wasting lot of memroty but giving consstan accessing. is a adt. use this

talk about python modle of copuation. why some operations are standard. Ram is the baisc model of commputaoin . pytohng omdel of computaton. what operation take less time.
and what not.

Eric lecture on models of computation.



If we wan to insert new object, we need to find a place for it, if we wan to delete/update we first need to find it.
The structre (how do we traverse or relation among elements) governs the way 

Importance of find/search operation:
find/search is so importatnt. it is prerequisite to other operations. For eaxmple, to insert in a position


 We explore how to better organize the data in memroy to achieve reasonalbe time.

As we
We are much interested in reaching the data we need.
Data is stored,

So, now assume we are solving a problem, simple one. A record.






Computer takes certain amount of time to do an operation on the data. 
Our goal when we talk about DS is that to make sure the time to do an operation is reasonable.
We don't want to wait to see the operation to be finished.


So it has a place to store the data. It is called Random Access Memory or main memory or simply memroy.




































Contigous memory: why should we mention size of memory while requesting?
determinism
Pointer based structuring. - heap.

*Refer the notes and other references.*

"call stack" vs heap memory
call stack - https://www.youtube.com/watch?v=aCPkszeKRa4
https://en.wikipedia.org/wiki/Stack_(abstract_data_type)#Software_stacks



traversing array is better than traversing LL?
https://www.quora.com/Is-it-faster-to-iterate-through-an-array-or-a-linked-list

Know about implicit-datastructures. array is implicit DS for heaps.
https://en.wikipedia.org/wiki/Implicit_data_structure

static vs dynamic data structures.
array is static. length is fixed.
list is dynamic it can grow or shrink




How all other data structures fit in this model.

- https://www.learncpp.com/cpp-tutorial/79-the-stack-and-the-heap/
- https://en.wikipedia.org/wiki/Data_structure

Built-in data types of different languges.
Data structure support in different languges.

The concept of *private heap*, a managed heap space.
https://docs.python.org/2/c-api/memory.html


OS, in its memory management, does protect memory from being accessed by other running programs.
https://www.cs.uic.edu/~jbell/CourseNotes/OperatingSystems/8_MainMemory.html

Handling big data in problem solving. http://homes.sice.indiana.edu/yye/lab/teaching/spring2014-C343/datatoobig.php
External algorithms




What computers can do?
RAM.
Random access memory.
Structuering data
ADT
implementation of ADTs

How programming languages like python provies implementations to the datastructues.
- https://wiki.python.org/moin/TimeComplexity


Dynamic storage allocation: https://users.cs.northwestern.edu/~pdinda/ics-s05/doc/dsa.pdf

