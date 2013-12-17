---
layout: page
title: Algorithm Complexity
unit: 6
uniturl: 06-searching-sorting
reading: 5
readingurl: 05-Algorithm-Complexity
---

Algorithm Complexity
==================
This lecture focuses on algorithm analysis, focusing on the following learning objectives:

 * 17: The student can appropriately connect problems and potential algorithmic solutions.
 * 18: The student can evaluate algorithms analytically and empirically.
 
 Introduction
------------
Let's play a number-guessing game (you have already seen this before).  

Between your partner and yourself, decide who will be the guesser and the the picker. The picker chooses a number between 1 and 50, privately. The guesser's role is to determine what the number is, and to that end asks the picker questions with the only possible answers being "yes" or "no".

The guesser should try two different strategies to playing this game:

Guessing in sequence: "Is the number 1?", "Is the number 2?", "Is the number 3?", and so on.
Guessing halfway: You know the number must be between 1 and 50, so you start off by asking "Is the number greater than 25?". If the answer is "yes", you instantly know that it must be between 26 and 50, so you ask "Is the number greater than 37?" (that is, halfway between 26 and 50). 

If the answer to the original question was no, the number must be between 1 and 25, so you ask "Is the number greater than 12?"
Play several times. The picker should pick a wide variety of numbers, while the guesser should use each strategy alternately.

As you play each game, think about the ways in which one strategy is better than the other. Which strategy would be better if, say, the guessing game involved numbers from 1 to 1000? From 1 to a million? From 1 to 3? 

Are there other stragtegies you can think of?

Competing with Young Gauss
------------
We would like to add all the numbers from 1 to N, where N could be a big number. The obvious way to do this is to simply add them up, one by one.


We can, however, also follow in the footsteps of the young Johann Carl Friedrich Gauss, a now-revered 18th century mathematician. As the story goes, he was punished by his elementary school teacher to do the same exercise: add all the numbers from 1 to 100. The teacher, J. G. Büttner, assumed that the problem would take Gauss a long time to do, yet Gauss finished the problem in a matter of seconds. He realized that, adding 1 + 2 + 3 + ... + 100 was the same as adding (1 + 100) + (2 + 99) + (3 + 98) + ... + (50 + 51). Each pair summed up to 101, and there were 50 of these pairs, so he quickly deduced that the answer was  101 × 50 = 5050. Presumably, teacher Büttner wasn't pleased.

In general, if you wanted to add the numbers from 1 to N, the answer would be 
     (N + 1) × (N ÷ 2), 
because there are (N ÷ 2) pairs, each of which add up to (N + 1).

Imagine that you are playing a game against young Gauss to see who could add numbers from 1 to N faster: he does it his way, while you manually add them one by one. You can either win, lose, or tie in this game. What do you think would happen if N is 2? If N is 10? If N is 100? If N is one million?
