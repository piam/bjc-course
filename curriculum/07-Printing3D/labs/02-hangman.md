---
layout: page
title: Guessing Game
unit: 5
uniturl: 05-lists
lab: 2
laburl: 02-hangman
---

Hangman
===
The goal of this homework assignment is to create a simple version of Hangman.

The player specifies the length of the word they'd like the use, and the computer picks a random word of the chosen length.from a list. The player then guesses a letter that they think may appear in the word. The computer checks whether the letter appears in the word and either reveals all instances of it (if it exists) or takes away one point from the player's lives. The computer then displays (somehow) the progress that the player has made towards guessing the word. The game continues until either all of the letters have been guessed (and the player wins) or all of the player's lives are used up (and the player loses). In either case, the computer should announce this event and the game should end.

Here is an example dialog. Words in parentheses are provided for clarity and do not need to show up in your actual output:

```
Computer asks: "How long a word do you want to play with?"

Human says 8.

(computer picks the word "fireball")

Computer: _ _ _ _ _ _ _ _

Human: r

Computer: _ _ r _ _ _ _ _

Human: a

Computer: _ _ r _ _ a _ _

Human: L

Computer: _ _ r _ _ a l l

Human: h

Computer: _ _ r _ _ a l l

Human: f

Computer: f _ r _ _ a l l

Human: e

Computer: f _ r e _ a l l

Human: i

Computer: f i r e _ a l l

Human: b

Computer: f i r e b a l l

Computer says "Congratulations! You figured out my word in 9 guesses and had 3 lives left!"
```

Starting Materials
-----

Start with an empty project.

You can use [this word list](http://bjc.berkeley.edu/resources/wordlists/words-1000.txt) as your computer player's word bank. Feel free to add / remove words or build a new list as well.

Tips and Thoughts
----
 * To read a list from a text file: save the file in an easily-accessible location (such as your desktop). Open Snap! and create an empty list in a global variable. Make sure the box next to the variable is checked to have it appear on the stage. Right-click or control-click the list on stage and you should see a dropdown menu, including an item that says "import." Select import, find your file, and open it. Each line of the text file will be imported as a new item in the list.
 * What do you think should happen if the computer doesn't know any words that are the length of the one specified by the user? Make sure to account for this in your program and leave comments justifying your design decision.
 * What do you think should happen if the player guesses a letter that they've already guessed? Make sure to account for this as well and leave comments justifying your design decision.
 * You can let the player start with any number of lives.
