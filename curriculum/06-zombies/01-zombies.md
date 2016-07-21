---
layout: page
title: Zombie outbreak!
unit: 6
uniturl: 06-zombies
lab: 1
laburl: 01-zombies.md
---

Learning Goals
--------------

* Practical skills

+ Learn how to write filters in spreadsheets
+ Handling data in an optimal way for cleaning purposes
+ Get experience with visualizing data using spreadsheets and maps
+ Creating/refining heuristics for working with data

* Soft skills

+ Familiarity with working with large data sets
+ Realizing how much can be tracked through social media/phone/VISA records
+ Understanding that data is not perfect
+ Cleaning data has consequences

Software Needed
---------------

Google spreadsheet (or any spreadsheet application that allows saving in CSV format)
Google maps (still need Google account)
Email

The Big Question
----------------

* What are some ways that your digital footprint can be traced? 
* How can we handle such large amounts of data to find meaningful patterns?

Lab Breakdown (2 week lab)
--------------------------

A mysterious virus has recently started spreading across the Lower Mainland. Infected individuals are becoming lethargic and sleepy with a big craving for braaaaains! The mechanism of virus transfer has not been determined but is suspected to be through sneezing or biting. Latency of the virus seems to vary across individuals. Virulence has been determined to be high and no transmission host has been identified yet.

Infections are increasing exponentially with each passing day and the Centre for Disease Control (CDC) is desperately trying to control this massive outbreak. The CDC has given you a list of individuals who have been hospitalized with this mysterious virus. You are the research scientists assigned to this case and your mission is to figure out who the very first infected patient is and determine how the virus was spread into the community.

* Download the list of hospitalizations [here]()**Link Needed**.
* Go to [Google SpreadSheets](https://docs.google.com/spreadsheets/). For remainder of the lab, you will need to have access to a Google account (remember, you can always make a Google account with false information!).

Using Google SpreadSheets
-------------------------
**We ask questions and dont give answers, let's change the style, by asking the question then having a spoiler that you hover over for the answer. This way we can encourage discussion between the partner**

![GoogleSpreadSheet](GoogleSpreadSheets.png)_

1. Make sure you are logged into a Google account and Go to [Google SpreadSheets](https://docs.google.com/spreadsheets/)
2. Click on the box with a + labelled Blank under "Start a new spreadsheet."
3. In your new spreadsheet, click on File -> Open -> Upload to upload the list from step 1.
3.5 **Give the sheet a new name**
4. To help us explore our data, we want to freeze the first row with our column headers while we scroll through the rest of the data. Click on View -> Freeze -> 1 Row.

Let’s explore our data.
-----------------------

6. Do all the data values make sense?
Answer: Did you notice a few people who where much older than a 100?
8. What should we do with the rows that have values that are suspicious? If we remove them, what do we risk?
Answer: It could be that patient 0's data get erased, perhaps if we had time we would look at multiple data sources and try to collaborate our data. But for this lab we will fearlessly delete data points that are wrong!
9. Is it possible to manually go through each and every entry to check for irregularities? 
Answer: Maybe but it would take a little bit of time and we could make mistakes and miss things
What if our data set was twice as big? 
Answer: Less likely
Or 4 times or 8 times larger?
Answer: At this rate we will quickly scale outside our ability to read all the values in a lifetime
10. What are some methods to quickly clean irregular values out of our data?
Answer: We can imagine defining a range and pulling any data outside this range out. There rae multiple ways of doing this, simply sorting the data and looking at it's highest and lowest values is a strategy we can use.
11. Since there are so many rows in the data, we don’t want to manually go through each row to look at the age of the patient. Let’s sort all the rows by age so that the oldest people are at the top of our document.
12. Click on any cell in Age column of the spreadsheet. Click on Data-> Sort Sheet by Column C, Z-->A.
13. The very oldest patients are now at the top of our spreadsheet. Delete any rows with ages that don’t make sense.
Hint: You should have found atleast **X patients** that should be removed.
14. Look at the Hospitalization Date column and sort the rows to see if there are any irregular dates. Remember to sort by both oldest to newest and newest to oldest.

Plotting data onto Google My Maps
-------

1. Given so much data, it can be useful to show the data in a visual form to help see any underlying patterns. Let’s visualize our data using My Maps.
2. Go to [Google My Maps](https://www.google.com/mymaps).

![GoogleMyMaps](GoogleMyMaps.png) 
3. Click on “+ Create a New Map”.
4. Under “Untitled Layer”, click on “Import”. In the window that follows, click on Google Drive, Recent and then choose the Google Sheet that has your data in it.
5. When asked which columns to use to position your landmarks, choose Home Address, Work Address, and School Address. 
6. Use Patient ID as the column to title the markers with.

[Mess of data](MessOfData.png)


It’s really hard to see anything with so much data. When working with large datasets, a common approach is to try and reduce the amount of data we are looking at based on some algorithm or method. For example, we might reduce the number of rows by filtering out all hospitalized individuals under the age of 60. Heuristics are not set in stone-- they can differ based on the problem you are working with.
Let’s apply a heuristic to the data by filtering on Hospitalization Date. Let’s sort 
Visualize the data in My Maps again. Has it helped you?

**(By the end of the lab, they should have a group of people who they suspect patient zero is. We need those PIDs for next week)**

Let’s Talk!
-----------

Do you feel like your current dataset was sufficient to help you figure out who patient zero is? What extra data would you want to help you answer this question? What kind of data can you realistically get? Cost of data cleaning.

Deliverable: 
-------------
Email your TA with the following subject title, <Section Number> CPSC 100 Data Visualization Lab Answers- Week 1. Emails received without this title will not be marked. Your email should contain answers to the following questions:
Why do you think you could not figure out who patient zero is?
What extra data do you think you want?


