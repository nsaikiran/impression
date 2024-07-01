---
layout: post
title:  "Practice"
description: "DSA"
categories: ["tech", "cs"]
tags: ["algorithms"]
author: "Sai Kiran"
---
## Problem practice notes

### Array based

#### Given an array of integers find the subarrays with sum K

Refer https://www.geeksforgeeks.org/find-subarray-with-given-sum-in-array-of-integers/ or https://www.geeksforgeeks.org/number-subarrays-sum-exactly-equal-k/ they are about the same problem.

- Brute force
Generate all the subarrays, calculate sum and check. [N-choose-2 possibile subarrays]() will be there.

- Better approach
While traversing the array, track the current sum, store the sum of array ending at each index in a hash map (sum and index mapping). Check if the K-currsum exists in the hashmap.

#### Number of substrings having an equal number of lowercase and uppercase letters

Refer Number of substrings having an equal number of lowercase and uppercase letters
It can be reduced to the above subarrays with sum K, where K=0 and each upper case letter is considered 1 and lower case letter is considered -1.
Reference: https://www.geeksforgeeks.org/number-of-substrings-having-an-equal-number-of-lowercase-and-uppercase-letters/

### Fast and slow pointers

- Classify the number in an array: Move all the odd numbers to beginnig of the array
- Remove zeros from the array
- Remove duplicate numbers from the array
- https://www.pramp.com/challenge/9PNnW3nbyZHlovqAvxXW

- Loop in a linked list

### Two pointers

- Given an array of integers find two elements who sum is K

### Dynamic Programming

Important points:
Break down the problem, write a recurrence that solves the problem. There are two approaches:

- Memoization/top-down
- Bottom-up/tabulation
Start from the smallest subproblems, solve them, save their solutions for reference. Each problem depends on the solution of smaller problems that are already solved. In this approach, we might solve the subproblems which may not be used later.
- [Fibonacci numbers problem by basecs](https://medium.com/basecs/less-repetition-more-dynamic-programming-43d29830a630)
- [0/1 Knapsack problem solution by striver](https://www.youtube.com/watch?v=GqOmJHQZivw)
- https://www.pramp.com/challenge/61ojWAjLJbhob2nP2q1O
- https://www.geeksforgeeks.org/largest-sum-contiguous-subarray/

## Problems to practive

- Classify elements in the array. Given an array classify the numbers as even, odd. Put all even numbers to the start of the array and odd numbers to the end. EPI arrays
- Find sum of most K recent numbers of a stream
Given a stream and when asked about most recent numbers, circular queue can be used know the implementation. Like moving sum or average etc
- Range sum problem
Given a array of numbers, implement some queries. Like rank of a given number, least number greater than some K, or greatest number less than K etc. Sort the array and do some preprocessing that will same somtime. This is on a static array, if that is a stream then we need to use someother approaches.
- Quick sort and merge sort code. Review once and write. How the merge step and pivot selection and placing it in right spot helps.
- H-Index problem: https://leetcode.com/problems/h-index/description/
- LRU cache implementation - ADT
- [LFU cache implementation - ADT](https://arpitbhayani.me/blogs/lfu/)
- Application of Ordered Set and its implementation. Python has OrderedDict,deque. Differences and their benefits.
- NGE using stacks
- Problems from https://github.com/Chanda-Abdul/Several-Coding-Patterns-for-Solving-Data-Structures-and-Algorithms-Problems-during-Interviews
    - all sections atleast 2 questions or 2 model of questions



## Previous questions
### Attempt 1
- Given a set of cartesian points, generate the bounding box that includes all the points.
- Given two strings, and we can cut the strings at same position. After cut we take the left half of the first string and right part of the second string and join them to form a new string. How many of those new strings are plindromes - https://cs.stackexchange.com/questions/109662/divide-two-strings-to-form-palindrome 
- Given a string with limited number of characters repeating. Find the number of substrings where the count of all allowed characters is same in the substring.
    -  Ex: RBRRB https://stackoverflow.com/questions/22604728/finding-substring-with-equal-number-of-characters 
- General json validation: string processing. Should have covered all of the edge cases. And validated the approached up front. So that I was confident while coding.
- Given start binary pattern and destination binary pattern, see if we can reach from start pattern to end, in each step only one bit can be flipped. Also given a set of safe states through which you should be traversing. Moving to a non-safe pattern in invalid. https://leetcode.com/discuss/interview-experience/515564/google-l3-hyderabad-feb-2020-rejected lock round 5
- Given a dictionary of words, suggest the user words based first few characters typed, like the functionality in mobile phone typing scenario.

### Attempt 2


### Blog remodeling
- https://reverie.pages.dev/
