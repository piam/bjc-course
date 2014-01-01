---
layout: page
title: All algorithms are not equal
unit: 6
uniturl: 06-searching-sorting
reading: 2
readingurl: 02-all-algorithms-are-not-equal
---


All algorithms are not equal
============================
This activity introduces the concept that algorithms are used to develop and express solutions to computational problems. It focus, in part, on the following learning objectives:

 * 15: The student can develop an algorithm.
 * 16: The student can express an algorithm in a language.
 * 17: The student can appropriately connect problems and potential algorithmic solutions.
 * 18: The student can evaluate algorithms analytically and empirically.

Comparing Algorithms
--------------------
We all know that computers can be really fast at solving problems: feed a computer a problem that adds several million-digit numbers, and the answer comes out faster than a human has finished the first ten digits. (Well, unless you're one of those [mental calculators](http://en.wikipedia.org/wiki/Mental_calculator).) In fact, that is one of the main motivations behind building computers: there are problems that humans can solve for small values, but once the values become large, it is better to ask a computer to do them instead, since a computer can crunch through calculations faster. Nonetheless, for many applications, speed is essential, and we can't trust a human to perform the calculations: [GPS](http://en.wikipedia.org/wiki/Global_Positioning_System), for example, would be a very different (maybe non-existent) system if a human were continuously determining the position of a plane or of a car.

In these applications, the faster, the better, so if we're faced with two algorithms to perform the same problem, we want to be able to compare which one performs better. Since computers are more useful for large amounts of data, we also want to compare the performances for large inputs. One obvious way to do this is to run both algorithms on large inputs, time each of the algorithms from start to finish, and see which one performs better. (We can also see which algorithm takes up more *space* in memory, but for today's lab, we will only focus on time.)

Can you think of any other tasks where speed is essential? In other words, can you think of any task that probably would not exist (or that would be very tedious!) if a human were in charge of performing it?

Time is of the Es-sense
-----------------------
We have seen how BYOB can be used to wait for a certain time before reporting anything. BYOB also allows us to do the converse: to report how long a program takes to finish. In the ```Sensing``` menu, you will see a command called ```reset timer``` and a reporter called timer:

![Timer](img-timer-1.jpg)

Activate (tick-mark) the timer reporter and you should see a timer ticking away above Alonzo. It's been ticking ever since you opened up BYOB, and counts in tenths of a second:

![Timer](img-timer-2.jpg)

We are going to be performing timing experiments in the following sections, so this timer will prove useful. Add the following timing framework script into the space for BYOB scripts:

![Timer](img-timer-3.gif)

The script will reset the timer whenever the green flag is pressed. Alonzo will then say Hello! for 1 second, and soon after that, he will say the current time, less 1 second to account for how long he said Hello!. If we replace Hello! with a reporter, then Alonzo will say the answer of the reporter, and one second later, how long the reporter took to generate the answer: this is the timing information that we need. Save the script with the name ```TimingFramework```.

Do You Have Time to Add?
------------------------
Let us start our timing experiments with something simple: how long does it take for a computer to add 1 to (or *increment*) a number? Replace Hello! in the timing script with an addition operator from the ```Operators``` menu, and add 1 to 100000 (that's five zeros!). Run the script a few times (around four) to get an idea of the average approximate time (in seconds) it takes for the computer to increment 100000. Run the script repeatedly by double-clicking on it; do not place the script inside a repeat or a repeat until block, since we are interested in knowing the approximate time the script takes to run once.

Now, pause here and think: what's your gut feeling for how much longer the computer would take if we doubled 100000? Test your intuition: Get an average approximate time for how long it takes the computer to increment numbers that you progressively double: 200000, 400000, 800000, and 1600000. Remember that for each number, you need to run the timing script multiple times (around four) to get an idea of the average approximate time (you don't have to be precise). What do you observe?

Take another huge leap and find out how long it (approximately) takes for the computer to increment numbers that you progressively scale by 10: 160000000, 1600000000 (that's eight zeros), and maybe 16000000000 (that's nine zeros). What do you observe?

Constant-Time
-------------
You may have noticed that the computer takes approximately the same time to increment a number, even though the number was made progressively larger. Computer scientists (programmers and theorists) thus call incrementing a number a **constant-time** operation. In fact, any basic arithmetic operation (addition, subtraction, multiplication, division, and exponentiation) is considered to be a constant-time operation.

Notice that we call these operations *constant-time* operations, but we don't actually say how much time they take. Different computers will take different amounts of time to perform the same operation. To report the exact time of any algorithm, we would have to also report the physical configurations of the computer that the algorithm was run on. This gets very difficult and annoying very fast, especially with the almost infinite variety of computers available today. Instead, we focus on how the running time of an algorithm scales as we scale its inputs to larger and larger sizes, because this is a property of the algorithm itself, and is independent of the computer that it is run on.

Why did the computer take approximately the same amount of time to increment a number, even though that number was getting larger? Think about how you would add one to a number, back from your elementary school days; this is similar to how a computer does its arithmetic (ignoring technical details). The elementary school way of adding numbers goes digit by digit, and so the amount of time it takes for you to add two numbers depends on how many digits each number has. As we doubled the number we were incrementing, we didn't consistently add digits to it, and so the computer took approximately the same time. Even as we began scaling the number by ten, the computer (and you!) takes a relatively really small amount of time to account for the extra digit, so the total time remains approximately constant.

Constant-time operations are the Holy Grail of computer science algorithms, and unfortunately, most algorithms are not constant-time, as we will soon see.

All the Numbers, All the Time
-----------------------------
For this section, we will be using [this timing framework](../code/timing.ypr). It is very similar to the framework you constructed earlier, but it also has the stubs for a few blocks that we will be filling in. The first block that we will fill in is already on stage:

![Timer](img-timer-4.gif)

This block should fill the input list with all of the numbers from start to end. If working correctly, the version used on stage should generate all of the numbers from 1 to max, where max is a number that we will change when running timing experiments, and should add them to the numbers list.

First, talk to your partner and discuss an algorithm that you can use to fill the input list with all of the numbers from start to end. Once you both have decided on an algorithm, complete the body of the block. Now, run the script with max set to 10. Run it a few times to get an idea of the average time the computer takes to generate this list (to the nearest tenth of a second); you don't need to be exact! Repeat the experiment with max set to 20, 40, 100, 200, and 1000. Do you see a pattern?

Linear Time
-----------
You may have noticed that if you increased max by a factor of two, then the computer took approximately twice as much time to fill the numbers list. Similarly, if you increased max by a factor of ten, then the computer took approximately ten times as much time; if you increased max by a factor of 100, then the computer ran approximately 100 times longer. In general, as we scale the size of the input by a certain amount, we also scale the running time by the same amount. We call these algorithms **linear-time** algorithms, because if we were to plot the runtime of one such algorithm against the size of its input, we would get a line.

Why is the algorithm a linear-time algorithm? When max was set to 20, we had to add 20 numbers to the numberslist; when max was set to 40, we had to add 40 numbers to the number list. In other words, as we scaled max, we also scaled how many numbers we had to add to the numbers list by the same amount. Linear-time algorithms are also much sought-after in computer science, and for many problems, they are the fastest algorithms you can find.



