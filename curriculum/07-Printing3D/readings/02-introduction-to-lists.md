---
layout: page
title: Introduction to Lists
unit: 5
uniturl: 05-lists
reading: 2
readingurl: 02-introduction-to-lists
---

Introduction to 3D-Models
========

In order to Print out an object in 3D we first need to create a model of the object we want to print. For this we are going to use [link](http://beetleblocks.com/run/).

This is a program much link Snap that you used in Lab's one and two. When beetleblocks open it will start with a tutorial, run through tutorial 1, but dont do tutorial 2!

![list](listblock.png)

Drag a list block into the scripting area to experiment with.
This block uses a Snap! feature you've seen once before, in the join block: a variadic input. This means that, even though you see one input slot in the block, you can give it any number of inputs. The left and right arrowheads at the end of the block are used to delete or add input slots:

![list](variadic.png)

Like any reporter block, the list block can be dragged into an input slot of another block

![list](saylist.png)

The grey rounded rectangle with red rounded rectangles inside it is the visual representation of a list. Each red rectangle is one list item.

The list picture has several extra widgets: a + button, the downarrow, and so on. When a list value is seen in a variable watcher, you can use these controls to modify the contents of the list directly. But we're not doing that for a while, so for now just focus on the values in the red rectangles.

*Try these*

What value do you get if you call the list block with no inputs? (Use the left arrow to delete the original input slot.)
Can you drag other reporters into list input slots to compute the list items?

What happens if you drag a list block into an input slot that expects a number as input, such as the inputs to the arithmetic operators?

What Good are Lists?
------
Let's say you're writing a program to generate English sentences. Your starting point might be various lists of words

![list](wordlists.png)

You could build up a sentence out of phrases. For example, to make a noun phrase, you want to pick one item from the articles list, one from the adjectives list, and one from the nouns list.

To select one item from a list, use the item block

![itemblock](itemblock.png)

List items are numbered from 1, so, for example, item 3 of the nouns list above is pizza. The first input slot accepts a number like other rounded input slots, but it also has a downward arrow that, when clicked, offers two special choices: last for the last item of the list, and any to pick an item at random.

The second input slot in the item block is something you haven't seen before: a rectangle with two orange smaller rectangles inside it. Just as a rounded input slot indicates that a number is expected, and a hexagonal input slot indicates that a true or false value is expected, this new kind of input slot means that a list value is expected. It's meant to look like what you see when you say a list: a grey (rounded) rectangle with red-orange rectangles for the individual items.

Use the item any feature to make a noun phrase by choosing a random article, a random adjective, and a random noun

![noun](nounphrase-block.png)

Because of the random item choices, we get a different result each time we call noun phrase

![nounphrase](nouphrase-calls.png)

*Try this*

Create blocks prepositional phrase, verb phrase, and anything else you need, ending with a sentence block that reports sentences like "the little elephant runs excitedly around the big pizza." Can you improve on this so that the sentence structure varies, sometimes including people's names instead of article-adjective-noun phrases, for example? You might want different sentence structures for transitive and intransitive verbs. This is an open-ended project!

Besides lists of words, you'll find uses for lists of numbers, to keep track of your grades in this course, for example, or to represent a sprite's position as a single vector (list) containing the X and Y position numbers. And you can even use lists of lists for more complicated data structures

![beatles](Beatles.png)


Transforming Each Item of a List
-----

In the last activity we made this list of nouns

![nouns](nouns.png)

Now suppose we'd like to be able to vary our noun phrases by sometimes using one of these nouns in the plural. So we need a way to add the letter "s" to each item of the list. Find the map block near the bottom of the Variables palette and use it this way

![join](map-join-s.png)

Snap! limits the size of list displays in speech balloons, so you only see the first three items of the result in this picture, but you can tell by the vertical slider and the "length: 7" that all seven elements are really in the result. If you want to see them all, drag down the bottom right corner of the list. 

![bignouns](bignouns.png) 

The first input to the map block has a form you haven't seen before this

![mapp](mapblock.png)

The grey ring means that the input should be a function. What we mean by this is basically the same thing as the f(x)=3x+7 kind of function in algebra, except that it doesn't have to be a numeric function. In this case the function we want is "join the letter 's' after the given word." When you drag the join block into the map input slot, the grey ring is still visible, to remind you that the input is a function, not the word that you'd get from some particular joining.

Instead of using a variable, like the x in f(x), to represent the input to the function, we leave one of join's input slots as an empty box. This is supposed to remind you of the notation 3×☐+7 ("three times box plus seven") that you learned for functions in elementary school before you knew about variables.


Try this: Modify your noun phrase block so that half the time it uses a plural noun. Note that, if you use a plural noun, the article has to be "the," rather than "a."

Here are some more examples of using map to compute some function of every item of a list:

![ex1](3x_7.png)

![ex2](ywd.png)

![ex3](squares.png)

In that third example, there are two empty boxes in the function, so it's ☐×☐, which squares each number.


*Try this*
In the last activity we made a list of Beatles

![beatles](Beatles.png)

Use map and this list to get a list of just the first names of the Beatles.

--------
![thebeatles](jpgr.png)

A function that, like map, takes another function as an input is called a higher order function. In the next two activities you'll meet two more higher order functions.

Choosing Some Items From a List
--------

You've probably played Geography, the game in which one player says a place name and the next player has to name another place whose first letter is the last letter of the previous place- Newark, Kentucky, Yonkers, San Francisco, Oklahoma. Have you ever gotten stuck on the letter "A"? Oklahoma, Alabama, Asia, Alaska, America, Alameda... and so on, forever.

How many states start and end with the same letter? To find out, we first need a list of all the states

![states](states.png)

Now we want to select a subset of the states, namely the ones whose first and last letters are the same. Here's the block we use for that

![predblock](keepblock.png)

Like map, the keep block has a function as its first input. Notice, though, that this grey ring's inner boundary is hexagonal. This lets you know that you should use a predicate function, which means a function that reports true or false.

We want to know whether two things are equal

![equal](equalblock.png)

The first letter of a word is letter number 1

![firstletter](firstletterblock.png)

(Note that we've deleted the word "world" that Snap! provides as a default value, a hint about what kind of input is expected. The input slot must be empty for our function-input notation to work.)

Finding the last letter is a little trickier; you find the length of the text and use that number to select which letter you want

![letterwanted](lastletterblock.png)

Putting all these pieces together will give us the answer we want

![keepsuchthat](geography.png)

You can see from the "length: 4" in the result that there are four such states. The one you can't see in this picture is Ohio.

But if you're playing Geography, the question you really want answered is "Which states start with such-and-such a letter?" You can define a block that takes a letter as input and gives the answer to that question

![statestart](state-starting.png)

![pstates](p-states.png)

![sstates](s-states.png)

*Try this*

Write an expression that will select all the words of at least five letters from a list. For example, if the words in the list are being, for, the, benefit, of, mister, and kite, then your block should choose the words being, benefit, and mister.

Write an expression that takes a list of mixed words and numbers, and selects just the numbers, (Hint: Look for is in the Operators palette.)

Write an expression that selects from a list of words the ones that start with a vowel. (Hint: Use contains in the Variables palette.)

Combining All the Items of a List
------
Let's say you have a list of numbers, such as all the students' grades on a quiz. You want to find the average grade. There are two steps: First, add up all the numbers; then divide that sum by the number of numbers â€” that is, by the length of the list.

![average](average.png)

Notice that the red length of block that finds the number of items in a list is different from the green length of block that finds the number of letters in a text string. 

The first input to the combine with block is a two-input function. In this case, it's the + block, because we want to add all the numbers. In fact, unlike the situation with the map and keep blocks, there are really only a handful of functions you'll ever use with combine

![badops](bad-operators.png)

Why did we include the addition and multiplication operators, but not subtraction or division? Using an operator with combine makes sense only if it doesn't matter whether the values are combined left to right or right to left. That is, 
3+(4+5) = (3+4)+5 
but 
3-(4-5) ≠ (3-4)-5

Very occasionally you'll define a two-input custom reporter for use with combine. The two-input max block is an example; try using that to find the largest of a list of numbers.

We should try out the average block

![avg](avg781.png)

Is that the answer you'd expect?

When you Really Have to Loop
----
Consider the following problem-

Write a predicate increasing? that takes a list of numbers as input, and outputs true if the numbers are in increasing order (equal neighbors are okay), or false otherwise.

![increasing](increasing-list-true-report.png)

![increasing](increasing-list-false-report.png)

Because this is a predicate, it's tempting to try to make it use keep

![wanabe](wannabe-increasing.png)

But map, keep, and combine work when each item in a list can be considered independently of the others. In this problem we have to consider each item in relation to the ones that have come before it: "Is this number at least as big as the ones we've already seen?"

To do this, we need to write a loop. The loop needs to go through the lists items, from left to right, and keep track of the last item that it saw. But, as with map, we don't need to keep track of the specific number of where we are in the list (e.g., the third position, the first position, etc.) Those index numbers have nothing to do with the problem we're trying to solve. The solution is to use the for each item block, this way

![increasing](increasing.png)

Like the functions used as input to map and friends, the script inside the C-shaped slot of for each item interprets empty input slots (in the < and set blocks) as placeholders into which an item of the list will be entered. For each item promises to go through the list starting with item 1 and continuing in sequence to the end of the list. We use a script variable minimum to remember the most recent item's value, which is the minimum allowable value for the next item. If any item is smaller than that remembered value, increasing? reports false. If we make it to the end of the list without violating that requirement, then increasing? reports true.

Note that the for each item block has the word "item" in a round orange block. It's a variable, and you can drag it into the script that goes inside the C-slot, instead of using an empty input to represent the list item

![increasing](increasing-item.png)
You can work with the above script here.

*Try these*
 * Display a longish list using time instead of space on the screen by saying each item for two seconds.
 * Write an expand reporter that takes a sentence as input, and reports a sentence that's the same except that each number in the input is replaced by that many copies of the following word
![sheloves](expand-she-loves-you3-yeah-with-report.png)
