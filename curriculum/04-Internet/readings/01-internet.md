---
layout: page
title: Internet
unit: 4
uniturl: 01-internet
reading: 2
readingurl: 01-internet
---


Fun with the Internet
=========================================

Learning Goals:
---------------
Use visual tools to better understand what happens under the hood when we load a webpage.

Visualize on a map at a high level how a packet is routed and forwarded.

Examine a visual representation of all the assets that a webpage requests/loads

Compare packet speed (light speed) to page loading speed (seconds) and be able to explain the descrepency

The Big Question this lab asks/answers:
---------------------------------------
If packets of information move at the speed of light what are some reasons that web pages can take a measurable amount of time to load?

Visualizing Internet Routes
---------------------------
Point your browser to this [internet route visualizing tool](http://www.monitis.com/traceroute/).

This will show you the route from a computer (by default in Washington) to another computer someplace in the world that you choose. 

![trace_route](trace_route.png)

Below we have a list of interesting servers from all over the world. Pick one or use your of your own choice by copy/pasting it into the input field at the top of the page and hit start. Make sure to try at least one server with interesting suffixes like .br, .au, or .tw.

*ct.cs.ubc.ca (Vancouver, Canada)
*www.mars.dti.ne.jp (Japan, Tokyo)
*mpi-sb.mpg.de (Germany)
*www.univ-paris1.fr (France)
*lanczos.maths.tcd.ie (Ireland)
*ida.liu.se (Sweden)
*alunos.ufv.br (Brazil)
*www.unb.br (Brazil)
*www.unsw.edu.au (Australia)
*mail.iis.sinica.edu.tw (Taiwan)
*rrzmta2.rz.uni-regensburg.de (Germany)

The green line you see is the route your packet takes to get to your server!

Now let's take a look at some of the data about it's trip, scroll down until you see a list of hops along with some times in ms.
Note that if traceroute can't find any data it will display a * for that hop.

![trace_info](route_table.png)

For each hop along the way that we have data for, we are shown the three times, each is the delay in ms that a packet takes to that router and back (known as RTT).

Notice that the RTT numbers are not the same, can you imagine why the time for a packet to get there and back would vary?

Answer:
!One reason could be that the network maybe more or less congested, much like a traffic jam.

Show your TA:

1. A server that you found that is the furthest away in distance
2. A server that you found that is the most hops away (can you get one longer than 20 hops?)
3. Be able to explain why the times there and back can vary.
4. Try to find a server that is the most hops away! Can you get one longer than 22?

Page Load Analysis
------------------

Now lets point our browser at this [Page Load Analizer](http://www.monitis.com/pageload/):

Now that we understand what's involved with sending data to and back from a server, let's take a look at what a page will load when we visit it.

Let's try looking at your favorite website, in our example we will look at a simple site such as ct.cs.ubc.ca. 

![simple_site](simple_site.png)

Take a look at the Domain column (3rd from the left), that is where we are requesting our data from.
This means that the data or packets will need to travel from that server to us along a route, which you have seen before.
On the right hand side you can see how long it took for that request to be fullfilled.

Try looking at a few sites with your partner then show your TA the following:

1. A website that loaded the most amount of different domains (can you get more than 5?)
2. A website that had the fastest total loadtime (can you get faster than 200ms?)
3. Be able to explain what factors make a website slow to load


