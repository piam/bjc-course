---
layout: page
title: Recursion in a Nutshell
unit: 7
uniturl: 07-recursion
reading: 2
readingurl: 02-recursion-in-a-nutshell
---


Recursion in a Nutshell
=======================
We have spent the last couple of labs learning about recursion. You have probably
realized that the technique for writing recursive blocks is relatively straightforward,
although the body of the block can be a bit tricky to figure out until you have gotten
enough practice, or have worked through several examples of what the block should do.

When performing recursion, we try to reduce a large problem into a series of similar,
smaller problems that can be solved in a similar ways. In fact, it is often best if we can
reduce the large problem into a collection of trivially small problems. For example,
finding the [factorial](http://en.wikipedia.org/wiki/Factorial) of a number is an
operation that is often written recursively because
each solution builds off of the solution before it (5! = 4! * 5; 12! = 11! * 12). It can be
written recursively as a set of trivially small problems (each step only multiplies two
numbers) that build up to a significant solution.

![Example](nutshell-img-1.png)

The process for writing recursive functions can be summarized in a few steps:


Step 1: Determine the base case
-------------------------------
The base case is the simplest possible solution to the
overall problem. In the example of the factorial, it is simple to find the answer
when the number provided is 1: the answer will always be 1. Every recursive
problem has a base case -- sometimes it will be straightforward and other times,
it may require a little more thought. What would be the base case for the
following recursive problems?
 * Searching through a list for the first occurrence of a particular number and
   replacing it with zero.
 * Counting the number of elements in a list.
 * Computing X<sup>Y</sup> , where X and Y can both be specified as arguments to the block.


Step 2: Choose a more complicated example
-----------------------------------------
Continuing our work on the factorial
problem, we will consider ![Example](nutshell-img-2.png). We could choose any
number here: 3, 5, 100, 24481, as long as it is not the base case. Hint: sometimes choosing
values right next to the base case (2, in this case) makes it harder to detect the
relationship in step 3, but any value outside of the base case will do.


Step 3: Consider an example that is slightly simpler (closer to the base case)
------------------------------------------------------------------------------
![Example](nutshell-img-3.png) might work here. Assuming we can get the answer
to ![Example](nutshell-img-4.png), how can we use its solution to help us figure
out ![Example](nutshell-img-5.png)? Figuring this out will allow us to determine
the "relationship" between solutions, which is a pivotal point in writing a
recursive function. In this case, 10! = 9! * 10, which shows a clear relationship
that we can represent in BYOB.


