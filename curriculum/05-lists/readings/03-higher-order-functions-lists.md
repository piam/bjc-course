---
layout: page
title: Introduction to Lists
unit: 5
uniturl: 05-lists
reading: 3
readingurl: 03-higher-order-functions-lists
---

Composing Higher Order Functions to Solve More Complicated Problems
=====

Suppose we want the squares of all the items of a list of numbers. That's a straightforward map problem

![map](mapsq.png)

Now suppose instead that we want to select the odd numbers from a list of numbers. It's a little tricky figuring out how to tell if a number is odd, but apart from that it's a straightforward keep problem

![keep](keepodds.png)

But what if we want the squares of the odd numbers? This is neither a simple map nor a simple keep, but combines aspects of both. And we can solve the problem by using the value reported by the keep as the list input to map

![mapsq](sq-odds.png)

Don't be confused about which inputs do and don't have rings. It's the square function and the are-you-odd? function that we use as the first input to each higher order function. But, even though keep itself is a function, it's the list reported by keep that we're using as the second input to map.


We're building up to one the great beautiful procedures you'll see in this course: We want to take a phrase, such as "Beauty and Joy of Computing," and report its acronym, the word BJC. You've explored two of the pieces of this problem in previous activities: 
- Select only the words with five or more letters.
- Make a list of the first letters of the words. 
Review those activities if you don't remember how to solve those problems.
But there are two more steps, one at the beginning of the problem and one at the end, both related to the fact that people (the users of your program) want to see words and phrases in the form of text strings, but as you've seen, it's much easier to compute functions of those words and sentences if we have them in the form of lists, so we can use the higher order functions you're learning.

To translate from a text string to a list of words, Snap! provides the reporter sentence->list (pronounced "sentence to list") that takes a text string as input and reports a list of words

![stol](stol-bjc.png)

As usual, you see only the first three list elements in the speech balloon, but you're told at the bottom that the length of the list is 5, as it should be for the five words in the given phrase.
Once we have the list, we can use the tools we've already built to get a list of the first letters of the long words. What we want, though, is a single word as the reported value. We can use one of the higher order functions to join the letters into a string.

Try this: Should we use map, keep, or combine for this purpose?
Here's the final result

![acronym](acronym.png)

![badacro](bad-bjc.png)

Oops! The word "Joy" is shorter than five letters, but it's still an important word in the acronym. We need a better algorithm.

*Try this*
Modify the acronym block so that, instead of keeping long words, it keeps words that start with a capital letter. (Hint: Experiment with the unicode of block.)

![bjc](good-bjc.png)

![byob](byob-acro.png)

More on Composition of Higher Order Functions
-------

![hof](fixed-acronym.png)

This is the corrected version of acronym that checks for words starting with a capital letter. Isn't it beautiful? It does a complicated job, so there's a lot packed in there, but think how much worse it would be if we didn't have lists to help organize such tasks. You'd take the text string phrase and write a loop to go through it, character by character, looking for spaces as word separators. Then you'd have to build up the result string, adding one letter at a time.

With map, keep, and combine, you can operate on the items of a list all at once. You don't have to think, "Find the first letter of the first word and operate on it, then increase the loop index until you find a space, then skip over any extra spaces that might be next to it, then remember the position of the beginning of the second word" and so on. You can think, "give me the first letters of all the words." 

(Instead, all that ugliness about looking for spaces is hidden inside the sentence->list block, where everyone writing an application about sentences can use it without having to reinvent it. This is another example of abstraction, which we mentioned right at the beginning as one of the central ideas of the course and of computer science in general.)

*Try this*

- Write a max block that takes two numbers as inputs and reports the bigger one (either of them, if they're equal). Use it, and the list tools, to find the length of the longest word of a sentence.

- Using that length to help, write a block that reports the longest word of a sentence (or the first word of that length, if there's a tie).

- Write a word->list block that takes a word of text as input, and reports a list in which each item is a single letter from the word. To do this, you'll have to use a loop, along with the add to list block:

![partial](partial-world-list.png)

- Imagine that you're writing a program to play Hangman. The program has thought of a secret word, and the user is trying to guess it. Write a display word block that takes two inputs, the secret word and a list of the letters guessed by the user so far. It should say the letters of the secret word, spaced out, with underscore characters replacing the letters not yet guessed

![hang](hang.png)

(Use your word->list block on the secret word to get started.)

- Write a reporter exaggerate that takes a sentence as input and reports an exaggerated version:

![exaggerate](exaggerate.png)

It should replace "good" with "great," "bad" with "terrible," "like" with "love," etc. And it should replace every number with twice the number.
