---
layout: page
title: Data Portfolio Project
unit: 9
uniturl: 09-data
lab: 3
laburl: 03-SPAM-vs-HAM
---

Spam vs Ham Data Activity
==============
A problem in the world is unsolicited mail, phone calls, and even visits from people selling unwanted 
things. The power of computers have, unfortunately, added electronic media, e-mails and text messages to 
the annoyance. Unsolicited advertising e-mails and text messages are very cheap to mass-distribute and 
therefore need only a very small return to be profitable.

These unsolicited electronic massages have been called SPAM. For an explanation on this, refer to this amusing 
[link](http://thedailyrecord.com/ontherecord/2011/05/09/why-spam-emails-are-called-spam/). The overall problem of spam 
is described in detail [in this Wikipedia article](http://en.wikipedia.org/wiki/Spam_%28electronic%29).

With spam becoming such a vexing problem, many statisticians and machine learning people have started working on 
ways to automatically decide whether a message is spam or HAM. (The common label for messages that are non-spam—
that is, messages you actually want—is HAM.)

In these activities, you will step into the shoes of a machine learning expert and think about ways to 
automatically classify real-world text messages as either ham or spam.

The Data
---------
You are going to work with a set of 500 real text messages, part of a collection recorded and collected by 
T. Almeida and J. Hidalgo [(original source)](http://archive.ics.uci.edu/ml/datasets/SMS+Spam+Collection).

Two typical lines in our data look like this:

ham	Fair enough, anything going on?
spam	SMS. ac Sptv: The New Jersey Devils and the Detroit Red Wings play Ice Hockey. Correct or Incorrect? 
End? Reply END SPTV

We've made a [starter Snap project](http://snap.berkeley.edu/snapsource/snap.html#open:http://www.corsproxy.com/beautyjoy.github.io/bjc-r/prog/data/spam-ham.xml) which you should open now. 
The text massages are in variable called datasheet that is a list of rows (like a row in the above table). 
Each row is also a list, but with only two elements: the first is the word spam or ham, and the second is 
the contents of the message. Be aware that this is real-world data with very casual langauge (we've already 
removed the messages with language that was too casual for a school assignment!)

We will call that first word—spam or ham— the ground truth classification. That is, at some point an actual 
human decided whether this message was spam or ham, and we'll consider this to be "the truth". In this way, 
we can see how good our program is at classifying a message, based only on its contents, by comparing it 
this value. You might actually disagree with some of the "truth" classifications that are in the file; if so, feel free to change them (and be ready to justify your belief to others!)

Out of the 500 messages, how many are ham?

The average number of words in a message
---------------------------------------
One approach to classifying messages is by separating them into individual words. In this activity, you'll do this 
and then look at the average number of words in ham messages versus spam messages. In the next activity, you'll
write a classifier based on what you've learned.

The following script might help you get started: it puts all the spam messages into a variable, and all the ham 
messages into another.

<img src="making-separate-spam-and-ham-lists.png">

With those separate variables, you should be able to calculate the average number of words of each kind of message more easily.

What's the average length of a spam message? Of a ham message?

Because the math isn't the point of the exercise, [here is a picture of a Snap block to calculate 
the average of a list of numbers]({{ site.baseurl}}curriculum/09-data/labs/average.png)

Classifying SPAM
--------------
Now that you know that the average length differs, build a simple classifier based on the number of 
words in a particular message. That is, write a block that takes in a message and, based on how many words 
it contains, returns either "ham" or "spam" as its classification.

<img src="classify-by-number-of-words-HAM.png">

<img src="classify-by-number-of-words-SPAM.png">

Implement in Snap, and use it to classify the messages in our data. You can use a regular loop to call your 
classify on the second item in each row of the data, or you might use this faster method using <img src="keep.png">

<img src="count-number-of-spam-messages-with-custom-classify.png">

Play around with different threshold values— that is, the number of words above which you decide that a 
message is spam.

What was the best threshold you found? How many messages did it classify incorrectly?

Better ways to classify?
------------------
What else could you do to improve the spam filtering?

Discuss this with your team. You might consider the following options:

 * Detecting spam by finding phone numbers or web links
 * Detecting spam by finding words that are highly frequent in spam messages and not in ham messages
 * Detecting spam by checking with a dictionary for clean spelling and no abbreviations 
 * Combining several methods
 * How hard would it be to implement your solutions? 

Do you think your solution would do better than the one you wrote earlier, on average number of words?
