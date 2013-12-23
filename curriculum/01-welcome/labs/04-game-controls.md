---
layout: page
title: Game Controls
unit: 1
uniturl: 01-welcome
lab: 4
laburl: 04-game-controls
---

Lab- Welcome to Visual Programming
==================================

Moving with the Arrow Keys
------------------
Often, we will want to move the character with the arrow keys (i.e. up, down, left, and right). We can use the 
block point in direction as shown below. 

<img src="point-in-direction-block.png">

In the next step, you're going to want two sprites with costumes; you could start with the earlier project making a 
Snap play.

There are still a few things in the Snap! user interface that you probably have not used yet. Experiment with the 
rotation controls shown below and make sure you understand the behavior of each. (Hint: it'll be more obvious if your 
sprite isn't pointing toward the right, and isn't wearing its turtle (arrow) costume.) These will probably come in handy 
at some point! 

<img src="rotation-controls.png">

Finally, make a character move around based upon the keys that you have pressed. You will need to use one of the 
rounded hat pieces, such as the one in the example shown below. These can respond to key presses and start a script. 
Use the four arrow keys to control the sprite motion. 

<img src="when-space-key-pressed-block.png">

Game of Tag
------------------
We are going to make a small game of tag in Snap!. Make a second set of four scripts, controlled by a 
different set of keys, for your other sprite.

We want one of the characters to react if the two characters touch. We can add the following script to the 
Duck sprite to say OH NOs!!! when it touches Alonzo. 

<img src="ohnos.png">

Note: One really important thing to note here is that once we click the green flag, the script 
above will always be running: notice that it always has a highlighted outline. Compare this to the script below 
that would only run once when you click the green flag. The functionality above is often called an infinite loop, 
and can be very helpful when we want something to continue running forever. 

<img src="ohno-once.png">

