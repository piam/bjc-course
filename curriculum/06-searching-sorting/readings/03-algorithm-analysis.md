---
layout: page
title: Algorithm Analysis
unit: 6
uniturl: 06-searching-sorting
reading: 3
readingurl: 03-algorithm-analysis
---


Algorithm Analysis
==================
This lecture focuses on algorithm analysis, focusing on the following learning objectives:

 * 17: The student can appropriately connect problems and potential algorithmic solutions.
 * 18: The student can evaluate algorithms analytically and empirically.


Introduction
------------
An algorithm's **correctness** refers to whether or not it contains errors. We will talk about testing procedures below.

An algorithm's **clarity** refers to how well it is expressed and described. Can you understand what it does and how it does it? We will begin using **comments** to document our code.

An algorithm's **efficiency** refers generally to how efficiently it uses two key resources, time and space -- i.e., the *processor or central processing unit* (CPU), and the computer's *main memory*, often called *random access memory* (RAM).

The faster the algorithm -- the quicker it finishes its task -- the more efficient it is with respect to time.

The less memory it uses, the more efficient it is with respect to space.


Sorting and Searching Algorithms
--------------------------------
In discussing this topic we will talk about *sorting* and *searching* algorithms. A **sort** algorithm arranges data in some order -- e.g., numeric or alphabetic order. A **search** algorithm looks up some target data -- e.g., a name in the phone book. You can think of the data as being contained in a **list**.


Efficiency and Input Size
-------------------------
Efficiency issues only come into play when there are large amounts of **data**. An algorithm's *input size* is often abbreviated with *N*. As *N* grows, the differences between efficient and inefficient algorithms become clear.

For example, this table shows the differences in running time in seconds for the same sort algorithm on different input sizes.

| List Size, N | Older Computer | Newer Computer |
| ------------ | -------------- | -------------- |
| 125          | 12.5           | 2.8            |
| 250          | 49.3           | 11.0           |
| 500          | 195.8          | 43.4           |
| 1000         | 780.3          | 172.9          |
| 2000         | 3114.9         | 690.5          |

Computer scientists like to *abstract away* the efficiency differences that are caused by different hardware and software -- e.g., faster vs. slower computer.

Here are some old data obtained on different machines when sorting 2000 integers using the same algorithm:

| Type of computer | Time   |
| ---------------- | ------ |
| Home PC          | 51.915 |
| Desktop PC       | 11.508 |
| Minicomputer     | 2.382  |
| Mainframe        | 0.431  |
| Supercomputer    | 0.087  |

**Empirical Analysis**: The data in both of these tables were gathered **empirically** or **experimentally** -- i.e., by running and timing the actual program on different machines and inputs.
Abstract Analysis

We can also analyze algorithm efficiency more abstractly, by comparing an algorithm to well known mathematical functions.

Consider the following graph with four functions : the logarithmic, linear, quadratic, and exponential functions:

 * Logarithm function:   y = log<sub>2</sub> x
 * Linear function:         y = 5x
 * Quadratic function:    y = x<sup>2</sup>
 * Exponential function: y = 2<sup>x</sup>

![Graph](img-graph.png)

    	

As you can see, as *X* increases, the running time increases. But look at the differences. Look at how slowly running time increases for the logarithmic function compared to the exponential function.

In terms of these four types of functions, we arrange the them in the following order in terms of how fast they increase as the size of, x, increases:

| logarithmic       | linear | quadratic     | exponential   |
| ----------------- | ------ | ------------- | ------------- |
| log<sub>2</sub> x | x      | x<sup>2</sup> | 2<sup>x</sup> |


Algorithm Efficiency
--------------------
Computer scientists like to characterize algorithm efficiency in terms of **how fast the running time will increase as the size of the inputs, *n*, increases**.

To see the dramatic differences, consider some numbers for these for types of functions:
    
| Inputs | Logarithmic     | Linear | Quadratic     | Exponential   |
| ------ | --------------- | ------ | ------------- | ------------- |
| n      | log<sub>2</sub> | n      | n<sup>2</sup> | 2<sup>n</sup> |
| 8      | 3               | 8      | 64            | 256           |
| 16     | 4               | 16     | 256           | 65,536        |
| 32     | 5               | 32     | 1,024         | 4,296,967,296 |
| 64     | 6               | 64     | 4,096         | 1.84 x 1019   |
| 128    | 7               | 128    | 16,384        | 3.40 x 1038   |
| 256    | 8               | 256    | 65,536        | 1.15 x 1077   |
| 512    | 9               | 512    | 262,144       | 1.34 x 10154  |

So, for 512 inputs, a linear algorithm could perform some task in 512 seconds. Whereas an exponential algorithm would take 1.34 x 10154 seconds.


Algorithms and Problems
-----------------------
Computer scientists like to analyze problems by asking, **what type of algorithm do we need to solve this problem**? Or, what's the fastest type of algorithm that can solve this problem?


A Linear Search Algorithm
-------------------------
For example, to find the number 100 in the following lists of numbers, we would have to go through each number in the list, from left to right.

    List 1 (16 numbers): (15  20  4  2  1  17  19  25  100   65  78  19 20  15  0  72)

    List 2 (16 numbers): (15  20  4  2  1  17  19  25  65  78  19 20  15  0    72  75)

We can use a linear search algorithm:

    # Search for X in List L and return its Index, indx,  in  L
    # Or return -1 if X is not in the List

    To Search for X in List L, DO:
       Set global indx to 1
       For each number, num, in the list, L:
          If num = X:
             Return indx      Set indx to indx + 1
       Return -1                                     # The number is not in the list so return -1

**TODO**: Hand trace this algorithm on List 1 and List 2 and count how many times you have to go through the loop.

**QUESTION**: Suppose there 512 numbers in our list. In the **worst case** -- i.e., when X is not in the list -- how many times would we go through the while loop?

This algorithm (and the problem it solves) are said to be **linear** because in the **worst case** it takes N iterations of the loop to find something in a list of N items.


A Logarithmic Search Algorithm
------------------------------
If our list were sorted -- e.g., like the telephone book -- then it wouldn't make sense to do a linear search -- i.e., start at page 1.

    List 1 (16 numbers): (1 2 5 6 9 12 15 16 32 64 100 128  256 299 512 568)

    List 2 (16 numbers): (1 2 5 6 9 12 15 16 32 64 99 128  256 299 512 568)

Instead we could guess the approximate location of the number in the list and look there. In the most general case, we could guess that the X was the middle value in the list. If X was greater (or smaller) than the middle value, we would search the top (bottom) half of the list.

This is known as the binary search algorithm. For example, to guess a secret number between 1 and N:

    Guess the middle value in the range 1..N
    If the guess is too high,
      cut off the top of the range.
    If the guess is too low,
      cut off the bottom of the range.
    Repeat until there's only 1 number left.

**QUESTION**: How many guesses to find the secret number between 1 and 100? Between 1 and 500?

You should be able to see that as N grows larger, the binary search will grow very slowly, like a logarithmic function.


A Quadratic Sort Algorithm
--------------------------
Let's look at an example of an algorithm that performs like a quadratic function. Sort a list of N numbers from low to high using bubble sort.

    List 1 (5 numbers): (10  5  4  4  1)

**NOTE**: Bubble sort is probably the world's worst sorting algorithm. And there are many sorting algorithms that are much more efficient. But here is bubble sort:

    # Sort the N numbers in List L into ascending order

    For a list of N items, repeat N-1 times.    #  N-1 steps
      For each adjacent pair of items                        #  N-1 pairs
         If the pair is out of order, swap the numbers

This algorithm contains a **nested loop**. The outer loop repeats N-1 times. And on each repetition the inner loop does N-1 comparisons of adjacent numbers. So that is N2 - 2N + 1 comparisons. That's quadratic.

**Clock analogy**: Think of the relationship between the second hand and the minute hand on a clock. The second hand ticks 60 times each minute. To time 1 hour, the minute hand would tick 60 times, which is 3600 seconds.

**TODO**: Hand trace this algorithm on List 1 and count how many times you have perform the IF statement?

**Question**: Suppose there are 512 numbers in the list and it took 1 second to compare and swap a pair of numbers. Approximately how many seconds would it take to sort the list?


Efficient Sorting
-----------------
Bubble sort is an example of an in-place sorting algorithm. It doesn't require much more memory than the list itself. The most efficient in-place sorting algorithms can sort N numbers in time that is proportional to an n log n function. For 512 numbers that would require time proportional to 512 × 8 = 8,192 seconds as opposed to 512 × 512 = 262,144 seconds.


A Linear Sorting Algorithm
--------------------------
What if we didn't care about conserving space? How fast could we sort N numbers?

    # Sort the list of N numbers in List L in ascending order. Suppose
    # the list contained numbers whose values ranged between 1 and M.
    # For example the numbers might be between 1 and 1000.

    (1) Make a list, LL, with M "buckets", each containg an empty list.
    (2) For each of the N numbers in list L, put it in its proper bucket.
    (3) Traverse through the list, LL, and empty the buckets back into the list, L.

For example, for our original list, (10 5 4 4 1) and assuming that the numbers range between 1 and 10:

    (0)  L =  ( 10 5 4 4 1)
    (1)  LL = ( () () () () () () () () () () )
    (2)  LL = ( (1) () () (4 4) (5) () () () () (10) )
    (3)  L  = ( 1 4 4 5 10 )

Questions
---------
 * **Space efficiency**: In terms of space, this algorithm requires space for the N numbers in L and the M buckets, so N + M. How much more space is this? Linearly more? Quadratically more?

 * **Time efficiency**: In terms of our N inputs, this algorithm grows linearly as the size of N grows.

This shows that for a given problem, different algorithms can have different efficiencies.


An Exponential Algorithm
------------------------
The [Traveling Salesman Problem](http://turing.cs.trincoll.edu/~ram/cpsc110/inclass/alg-analysis/) is an example of a problem that can only be solved using an *exponential algorithm*. Given N cities, find the shortest path (least costly path) through all N cities.

The only known way to solve this problem is by **brute force**. List all possible paths through the cities. For 3 cities we can easily do this:

    A B C
    A C B
    B A C
    B C A
    C B A
    C A B

In general there are *N!* ways to arrange *N* cities. So there are 3 × 2 × 1 = 6 ways to arrange 3 cities. And in general *N!* is much greater than *2N*:

| N | N!  | 2N  |
| - | --- | --- |
| 3 | 6   | 8   |
| 4 | 24  | 16  |
| 5 | 120 | 32  |
| 6 | 720 | 64  |

Problems that can only be solved by *exponential algorithms* are known as **intractable problems**. There is no general, optimal solution for the traveling salesman problem that runs in a reasonable amount of time.

There are **heuristic** solutions. A *heuristic* is a rule-of-thumb that gives a pretty good (but not always optimal) solution. For the traveling salesman problem we can use the nearest-neighbor heuristic -- i.e., select the nearest neighboring city as the next city.
Computability

Theoretically speaking, not practically, are there problems that cannot, in principle, be computed? We're not talking here about *practical* limits to computation.

The answer is "No". In 1936 British Mathematician [Alan Turing](http://en.wikipedia.org/wiki/Alan_Turing) proved that there is a set of problems that cannot be solved by any algorithm or computational procedure.

Example: [The Halting Problem](http://en.wikipedia.org/wiki/Halting_problem). Given a description of a computer program, determine whether the program halts or continues running forever. In other words, given a program and an set of inputs, decide whether the program will eventually halt given that set of inputs.

Turing proved that there is no general algorithm that can solve the halting problem for any program and any inputs.

We won't go into the details here, but it's important that you know that computers do have this limitation.


Exercises
---------
Do the following exercises and add your answers to your Portfolio page for today's assignment.

For each of the following problems, decide whether it can be solved by a *linear* algorithm and explain briefly why or why not.

 * Compute the sum of a list containing N random integers.
 * Determining if duplicate numbers occur in a list of N random integers.

For each of the following problems, decide whether it can be solved by a *logarithmic algorithm* and explain briefly why or why not.

 * Guessing a number between 1 and 100 if your guesses are characterized as "too high" or "too low".
 * Guessing a number between 1 and 100 if your guesses are characterized as "wrong" or "right".

For each of the following problems, decide whether or not it is *intractable* and explain briefly why or why not.

 * Computing the sum of all the numbers in a square matrix of dimension N × N.
 * Given n integers does there exists a subset of them that sum exactly to B? For example, suppose the integers are {4, 5, 8, 13, 15, 24, 33}. If B = 36 then the answer is yes (and 4, 8, 24 is a solution). If B = 14 the answer is no.

