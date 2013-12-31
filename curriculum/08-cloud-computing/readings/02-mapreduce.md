---
layout: page
title: What is Cloud Computing?
unit: 8
uniturl: 08-cloud-computing
reading: 2
readingurl: 02-mapreduce
---


The MapReduce Distributed Computing Pattern
========

Distributed computing is a field where many computers (often geographically remote) are used to solve a single problem.

As you can imagine, the mechanisms of this are quite complicated. Traditionally, distributed programming has been difficult (at least compared to programming on a single computer with one core).

The scientific community deeply cares  about this issue because they often have so many computations that can only be done in a distributed way (e.g. simulating climate change). Very early distributed computing applications were all scientific in nature.

More recently, every field has large datasets and computing jobs, from entertainment (Pixar rendering a frame from their latest movie) to medicine (protein folding), to finance (running simulations of a new purchasing strategy on all historic stock exchange data) to artificial intelligence (solving checkers), and to business (Google needing to crawl and index and search the web).

Languages and tools and abstractions have improved greatly for distributed computations.

At the end of the day, Amdahl's law tells us that in the perfect world, if we distribute the problem across N machines, we can solve the problem N times faster. However, it will be hard to get that level of speed-up because of serial fraction of code. Still, if N is on the order of a million and coders make every effort to reduce the serial fraction, that is a pretty fast system!

Common patterns have emerged (i.e. the best ways) to approach problems with computational resources which might be geographically distant.

One of these patterns is MapReduce, which has emerged as a remarkable abstraction for dealing with the difficulties of distributed computing.

Researchers at Google wrote the seminal paper on it, and they use it extensively to take advantage of their massive datacenters to help them with their massive data needs. In our simplification of the process --

There is a Map phase where (sometimes very big) data is broken up into pieces and sent to machines with a mapping function. Sometimes the mapping function is the identity (i.e. do nothing) function; take what is sent in and return it. The output of the mapper is the same as the input of the reducers. In our simplifying abstraction, the mapping happens over a list of elements, which can be of any type (word, sentence, list, procedure, etc.).

There is a Reduce phase where all the results of the mappers are combined into one using a reducing function, which takes two adjacent pairs and replaces those values with the reduction of those two values. This process continues until there is only one element left.

Note that the outputs of reductions are sent as input to other reducers, so in our simplifying abstraction, there are only two data types:

The data type used in the list of input to the mappers. In the tables below, the Input is a list of this type. (e.g., if the input is a number, then the input to the MapReduce is a list of numbers.)

The data type that is the output of the reducers, shown as Output below, is the reported value of the entire MapReduce process. In this simplified model, this type is the same as the output of the mappers, which is the same as the input to the reducers.

Another way to think about it -- what if the original list were of length 1? The mapper would do its job, and return something. But, since it is the only mapper needed, its output has to match the desired output of the MapReduce call, so every mapper always has to return the same output (type, formatting, etc.) as is desired (from the result of the reducing phase).

Here is the most important part of this, so read the following over a few times so you understand: Thanks to Abstraction, running a MapReduce on your computer should be indistinguishable from running MapReduce on a cluster of a million computers (except hopefully the latter is faster). You do not need to worry about that when you are writing your MapReduce code. So for this lab, we are going to make sure you understand how to write MapReduce programs for one computer, and later when Snap! allows us to easily support automated, distributed computing, the internals of MapReduce will change to send your program to a cluster, but your programs will not have to!

How does it work? It is exactly as we describe -- we send the results of mapping over a list to a reducer (block interface and definition shown below).
