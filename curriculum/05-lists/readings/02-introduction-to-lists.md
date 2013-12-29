---
layout: page
title: Introduction to Lists
unit: 5
uniturl: 05-lists
reading: 2
readingurl: 02-introduction-to-lists
---

Introduction to Lists
========

Look in the Variables palette below the orange variable-related blocks for a bunch of red blocks. These blocks are about lists. A list is a way to combine several values into one grouped value.

The first red block is the list block, used to create a list

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

![nounphrase](nounphrase-calls.png)

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

![ex3](swuares.png)

In that third example, there are two empty boxes in the function, so it's ☐×☐, which squares each number.


*Try this*
In the last activity we made a list of Beatles

![beatles](Beatles.png)

Use map and this list to get a list of just the first names of the Beatles.

![thebeatles](jpgr.png)

A function that, like map, takes another function as an input is called a higher order function. In the next two activities you'll meet two more higher order functions.

