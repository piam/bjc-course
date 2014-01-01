---
layout: page
title: Recursive Bunnies
unit: 7
uniturl: 07-recursion
lab: 2
laburl: 02-recursive-bunnies
---


Recursive Bunnies
=================
Use Snap to create a recursive procedure to count the number of bunny ears given a number of bunnies entered. Use the Factorial or OddNumSum program as a guide. Remember, there are two ears per bunny (unless you have “different” bunnies).

Your code MUST be recursive - You should have a function (block) to count the ears that calls itself!


HINT
----
Looking a Factorial in our example and OddNumSum we can see that our recursive call should look something like:

The Number of Ears + BunnyEars (Number of Bunnies - 1)  where BunnyEars is my recursive function block name and I have a variable to represent "The TOTAL Number of Ears" and the "Number of Bunnies" and the "Number of Ears" would be 2. . .

because we want to add 2 (or 3) ears to the total of the smaller group of bunnies. Right?


EXTRA POINTS
------------
To earn extra points modify your script code so that:

The ODD number bunnies have 3 ears and the EVEN number bunnies have 2 ears.

For example: I have 5 total bunnies. This means that bunnies #1, 3, and 5 have 3 ears each for a total of 15 ears and bunnies # 2 & 4 have 2 ears each for a total of 4 ears. So my output would say "There is a total of 19 ears."

By the way, you can have 2 recursive calls inside your script as long as there is conditional execution. In other words, If _____________ do the recursive call this way Else do the recursive call that way.



