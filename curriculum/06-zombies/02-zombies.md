---
layout: page
title: Zombie outbreak!
unit: 6
uniturl: 06-zombies
lab: 2
laburl: 02-zombies.md
---

Week 2
======

Let’s Talk!
-----------

Last week, we talked about getting some extra data to help figure out who patient zero is and how patient zero spread the virus across the Lower Mainland. This week, we managed to get some extra data for you by mining cell phone data, Facebook check-in, Instagram metadata, VISA records, and Google tracking history. We’ve managed to find where people have gone in the last fifteen days. 

What should you do with the data now?
Talk about what info you can get out of it by combining the two datasets?
Remind them that they have a group of people they are interested in
Do we want to have an ethics discussion about whether or not tracking should be turned on?

Find the data here. (put link to data here)
Try importing the data into Google Maps. Does it help? (Should we bother? It seems kind of pointless since we already did this last week)
Take the PIDs of the possible patient zero candidates and only map the locations of those people.
Can you find one person whose path intersected with all the others? If you can’t, did you manage to narrow down the patient zero candidates? Who are they?

Deliverable
-----------
Email your TA with the following subject title,** <Section Number> CPSC 100 Data Visualization Lab Answers- Week 2**. Emails received without this title will not be marked. Your email should contain answers to the following questions:
What is the pid of patient zero (give pid) or what are the pids of the group of people you think patient zero is in? 
What method did you use to come up with your answer? 
Why do you think you correctly identified patient zero? Were there any places in your methodology where error could have been introduced? (Just briefly tell us this in a few sentences. Do not exceed four sentences- anything after four sentences will not be marked). 

Lab Discussion continued
Set the stage for the next step where we tell them we mined facebook/instagram/visa/cell phone records to find the places they were prior (maybe tell them about how they can be tracked)
Give them what we have


steps:

* disable view of week 1 infections
* plot only earliest infected an donly loc data
* click paint roller icon and "Sytle by PatiendID" this gives each person it's own color.
* if you have few enough people you can plot a path (I have 16+ and cant see different colors)


** bugs **
myMaps crashes a lot
sometimes erros (at times I couldn't add more than 3 layers, while sometimes I can, we should keep it to 2)
myMaps isn't plotting more than one location if I try to do it all at once.

** Solution **

Home+work only, 3 layers can break things
Early infection + data cleaning should just give us 3 pid's
We can then route them by hand? or we fix this bug by finding a work around.


<screenshot: correct>


Use overlap data by seeing who the people in the first set of infections have interacted with to find a link
Visualize to see if you can figure out the path that patient zero took
Come out with patient zero

Deliverable: Who do you think is patient zero (give pid) or which group of people is patient zero in? What method did you use to come up with that answer? Why do you think this? (Let them know we only want a few sentences, no need for an essay). Email it to the TA (need specific email title with section, and name else don’t mark it).



