---
layout: page
title: Make a recursive tree
unit: 7
uniturl: 07-recursion
lab: 4
laburl: 04-c-curve
---


Make a Recursive C-Curve
=====================

We can make very very complex images by just repeating the same shape multiple times. You'll be writing the recursive function to draw the c-curve. Below the base case is that the sprite draws a single line. The sprite starts facing right and faces right at the end. (Hint - the direction that the sprite points at the end is important! It should point in the same direction it did at the beginning of the recursive call.)
![img1](c-curve-level0.gif)

In the next level, start facing right and end facing right but repeat the previous level twice (red and blue below).
![img2](c-curve-level1.gif)
In the next level, start facing right and end facing right but repeat the previous level twice (red and blue below).
![img3](c-curve-level2.gif)

In the next level, start facing right and end facing right but repeat the previous level twice (red and blue below). 
This continues for each of the following levels, but you should probably focus on the trying to think through 
the first few levels.

If it's helpful to you, use the same technique we showed in writing the tree program: Start with a flake1 block that handles the base case, then write a flake2 block, then flake3, and so on until you understand the pattern.

![lvl3](c-curve-level3.gif)
![lvl4](c-curve-level4.gif)
![lvl5](c-curve-level5.gif)
![lvl6](c-curve-level6.gif)
![lvl7](c-curve-level7.gif)
![lvl8](c-curve-level8.gif)
![lvl9](c-curve-level9.gif)
![lvl10](c-curve-level10.gif)
![lvl11](c-curve-level11.gif)
