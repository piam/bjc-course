---
layout: page
title: Fundamentals of Game Design
unit: 11
uniturl: 11-game-development
reading: 2
readingurl: 02-fundamentals-of-game-design
---



The Fundamentals of Game Design
===============================
October 12th, 2010

I got a request via Twitter for this old essay which had fallen off the Internet, so I am posting it here. This was originally written for Metaplace users... there is nothing here new to anyone who has followed the blog for a while, but since it was requested, here it is. 

The fundamentals of game design
-------------------------------
Starting out creating an interactive experience, of any sort really, can be rather daunting. In this tutorial, we’ll run through the basic components of a game, so we can get a handle on what the next steps are when you make the jump from the training tutorials to your own projects.

Often people have trouble when conceptualizing a game. The idea, after all, is often the easy part. It’s actually making it, and figuring out where to start, that is the hard part.

A friendly warning, though! Just like writers have different ways of working, and some composers write music in their head and others at an instrument, different game designers are going to have different ways of working. Some work better “in the code” and others like doing everything on paper beforehand. Some think in terms of story and narrative, and others are systems designers first and foremost. So this tutorial may actually run a bit against the grain for you, depending on your natural temperament.

In what follows, I am going to use the language of games, but really, every piece of advice in this article applies equally if you are designing any sort of interactive project whatsoever. So just because I say “game” in what follows doesn’t mean this article won’t be useful to you when you start making a classroom experience or a chat room or some other application.


The components of a game
------------------------
The first thing to understand is that games are made out of games. A large game is actually composed of minigames. Even a small game is built out of very very simple small games. The smallest games are ones that are so simple and stupid, you can’t lose. You can think of this as “game atoms,” if you like.

For example, in the classic puzzle game Tetris, the basic game is beating your high score. To beat that game, you have to master the game of forming lines. There’s actually multiple variants there, because you have to learn the games of placing all the different sorts of blocks. And finally, the simplest game is rotating a block, which is just a button and hard to screw up.
So games are built out of games. This brings us to key piece of advice #1:

Advice #1: Design one game at a time.
-------------------------------------

Turtles all the way down
------------------------

Even if you are making a complex game, built out of many “game atoms,” each atom is a game in its own right, and has to feel fun and satisfying. Even the stupid ones with no challenge have to feel good. Imagine how poor a game Tetris would be if the stupidly trivial game of “press a button and watch the block spin” wasn’t satisfying.

Many games are ruined at this very fundamental level by poor design. For example, a bad designer might have decided that a random chance of the block not rotating would make sense. After all, we use random chance in gambling, board games, and roleplaying games, right? But it would make Tetris unplayable.

Game atoms
----------
OK, so you’re going to design one of the game atoms. Luckily, every game atom has the same characteristics:

 * A player does something.
 * The opponent (which might be the computer) calculates a response
 * The player gets feedback.
 * The player learns from this feedback, and gets to do something again.

You can think of these steps in very abstract terms:

 * Input
 * Model
 * Feedback
 * Mastery
 
Really, that is it. Let’s apply it to our Tetris example again. At the trivial “rotate a block” level, we have

 * A player hits a button.
 * The computer calculates that this means rotate the L counter-clockwise.
 * The player is given the feedback of the block in its new position.
 * The player figures out “I bet I can do this with other sorts of blocks too. And there’s probably a rotate clockwise button somewhere. Rotating is my goal!”
 
 
Advice #2: make sure the controls match up well to what the player is attempting to do
--------------------------------------------------------------------------------------

At a more advanced level we have
 * A player can rotate left, right, drop a block, glance at the next block, etc. Lots of choices.
 * The computer is going to take its turn and move the block further down regardless, or spawn a new block of a random shape if there isn’t one.
 * The block moves down. Maybe it completes a line, maybe it doesn’t.
 * The player says “aha! Completing lines is my goal, and different shapes help or hinder that!”
 
Notice that if any of these four steps is poorly chosen, the whole game sucks.
 * A player moves the mouse.
 * The computer figures this means rotate a block.
 * The player is not shown the block, but instead a stock quote.
 * The player is baffled and quits.
 
 
Advice #3: make sure the player can actually learn from the feedback you give them.
-----------------------------------------------------------------------------------
Where does the fun come from?

The fun comes from the mastery process. But what the player is mastering is the model. All games are mathematical models of something. We often speak, for example, of Chess being like war (we actually speak of lots of games as being like war!).

Even games like Tic-Tac-Toe are expressible as math puzzles. Games of resource management over time (like an RTS or Civilization) are exercises in calculus. RPGs where you make choices in character building are actually examples of exploring possibility spaces searching for local maxima… games lie to us all the time about what they are really about.


Advice #4: try to stop thinking about what your game looks like, and think about what it is actually modeling
-------------------------------------------------------------------------------------------------------------
The underlying math

All this sounds incredibly geeky, but you don’t have to be a math geek to enjoy games. The trick is to make the pill go down easy. And the fact is that some math problems and models are more interesting than others. Nobody is that interested in a game that pushes you to solve “2×5 = ?” over and over. It has to be a sort of problem that you can come to again and again, and explore possibilities looking for alternate solutions and paths.

This means that there’s a specific and highly varied set of problems that make for good games. In math, a lot of these problems are what is called NP-Hard problems. You don’t need to dig into higher mathematics to be a good game designer, though. Instead, you need to ask yourself a basic set of questions:

 * Where?
 * When?
 * How?
 * What?
 * With?
 * For?
 * Few?
 * Phooey.

This list seems facetious, but it’s a shorthand way of asking yourself the following questions about your game atom:

 * Do you have to prepare for the challenge?
 * …where prep includes prior moves? …and you can prep in multiple ways?
 * Does the topology of the space matter?
 * …does the topology change?
 * Is there a core verb for the challenge?
 * …can it be modified by content?
 * Can you use different abilities on it?
 * …will you have to in order to succeed?
 * Is there skill to using the ability?
 * …or is this a basic UI action?
 * Are there multiple success states?
 * …with no bottomfeeding? …and a cost to failure?
 
You have to answer yes to all of these for your game atom to be fun. And yes, we mean every atom in the game has to meet these criteria.

Advice #5: check this list for every action a user can take, every decision they make
-------------------------------------------------------------------------------------

How do you get there?

There’s really only one way, right now. You prototype and iterate. Don’t get hung up on the visuals, except for worrying about whether you are giving enough feedback. The best games can be played using sticks and stones. (You can play most roleplaying games with pretty much any random chance generator, for example).

You can prototype with all sorts of things. I have a “prototype kit” because I often prototype using physical objects before going into the code. It consists mostly of stuff that I can pick up at a craft store:

 * Two decks of regular cards.
 * One deck of Uno cards.
 * One Go board.
 * One Checkers board.
 * A half dozen six-sided dice.
 * One full set of polyhedral dice.
 * A large stack of differently colored index cards.
 * Twelve pounds of differently colored beads. Go to the pottery aisle at your local craft store — these are the kind that get put in fish tanks and potted plants. It’s a bit more than a buck for a pound of one color.
 * Wooden pieces, also from the craft store. These are found in the aisle with the clock faces:
 * wood cubes, various sizes
 * colored flat squares, three sizes
 * dowel rods
 * ‘pawn’ pieces
 * wooden chip (circles)
 * assorted circles, hexagons, stars, etc
 * Blank wooden clock faces that you can draw boards on.
 * Wood glue
 * Dremel tool
 * Square glass chips (also from the craft store, asst colors)
 
But even that is overkill for most people.


Advice #6: watch others play your game
--------------------------------------
You’ll quickly see where you didn’t provide enough feedback, or where they can’t figure out the underlying model.


A final thought
---------------
Fundamentally, never forget that if you want to design, you have to just go do it. The only way to get better at it is to keep doing it, because gamemaking is in itself a great and varied game to play.

*Article copied (and gently modified) from Raph Koster’s Website located at  http://www.raphkoster.com/2010/10/12/the-fundamentals-of-game-design/*

