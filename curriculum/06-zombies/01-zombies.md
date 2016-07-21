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

What are some ways that your digital footprint can be traced? How can we handle such large amounts of data to find information?

Lab Breakdown (2 week lab)
--------------------------

A mysterious virus has recently started spreading across the Lower Mainland. Infected individuals are becoming lethargic and sleepy with a big craving for braaaaains! The mechanism of virus transfer has not been determined but is suspected to be through sneezing or biting. Latency of the virus seems to vary across individuals. Virulence has been determined to be high and no transmission host has been identified yet.

Infections are increasing exponentially with each passing day and the Centre for Disease Control (CDC) is desperately trying to control this massive outbreak. The CDC has given you a list of individuals who have been hospitalized with this mysterious virus. You are the research scientist assigned to this case and your mission is to figure out who the very first infected patient is and determine how the virus was spread into the community.

Download the list of hospitalizations here.
Go to https://www.google.ca/sheets/. For remainder of the lab, you will need to have access to a Google account (remember, you can always make a Google account with false information!).

Google Sheets
-------------

Click on the “Go to Google Sheets” button and a new tab will appear.
Go to the new tab and click on the “+” sign to open a new spreadsheet.
In your new spreadsheet, click on File -> Open -> Upload to upload the list from step 1.
To help us explore our data, we want to freeze the first row with our column headers while we scroll through the rest of the data. Click on View -> Freeze -> 1 Row.
Let’s explore our data.
Do all the data values make sense?
What are some values that don’t make sense? Look in the Age column to see if all the values there are reasonable.
What should we do with the rows that have values that are suspicious? If we remove them, what do we risk?
Is it possible to manually go through each and every entry to check for irregularities?
What are some methods to quickly clean irregular values out of our data?
Since there are so many rows in the data, we don’t want to manually go through each row to look at the age of the patient. Let’s sort all the rows by age so that the oldest people are at the top of our document.
Click on any cell in Age column of the spreadsheet. Click on Data-> Sort Sheet by Column C, Z-->A.
The very oldest patients are now at the top of our spreadsheet. Delete any rows with ages that don’t make sense.
Look at the Hospitalization Date column and sort the rows to see if there are any irregular dates. Remember to sort by both oldest to newest and newest to oldest.

My Maps
-------

Given so much data, it can be useful to show the data in a visual form to help see any underlying patterns. Let’s visualize our data using My Maps.
Go to https://www.google.com/mymaps. 
Click on “+ Create a New Map”.
Under “Untitled Layer”, click on “Import”. In the window that follows, click on Google Drive, Recent and then choose the Google Sheet that has your data in it.
When asked which columns to use to position your landmarks, choose Home Address, Work Address, and School Address. 
Use Patient ID as the column to title the markers with.

<screenshot Mess of data>


It’s really hard to see anything with so much data. When working with large datasets, a common approach is to try and reduce the amount of data we are looking at based on some algorithm or method. For example, we might reduce the number of rows by filtering out all hospitalized individuals under the age of 60. Heuristics are not set in stone-- they can differ based on the problem you are working with.
Let’s apply a heuristic to the data by filtering on Hospitalization Date. Let’s sort 
Visualize the data in My Maps again. Has it helped you?

(By the end of the lab, they should have a group of people who they suspect patient zero is. We need those PIDs for next week)

Let’s Talk!
-----------

Do you feel like your current dataset was sufficient to help you figure out who patient zero is? What extra data would you want to help you answer this question? What kind of data can you realistically get? Cost of data cleaning.

Deliverable: 
-------------
Email your TA with the following subject title, <Section Number> CPSC 100 Data Visualization Lab Answers- Week 1. Emails received without this title will not be marked. Your email should contain answers to the following questions:
Why do you think you could not figure out who patient zero is?
What extra data do you think you want?


Import Data (Google Spreadsheets) 
Clean/Filter (Google Spreadsheets)
Visualize (My Maps)

<screenshot Mess of data>



Apply Heuristic (sort/filter by age, or time)
Visualize 

<screenshot Mess of blobs of data with Gaussian blur>


Lab Discussion (We need more data “Relationships”)
Survey lab for what kinds of data they want
Talk about what’s feasible

Deliverable: Why do you think you could not figure out who patient zero is and what extra data do you think you want? Email it to the TA (need specific email title with section, and name else don’t mark it).






