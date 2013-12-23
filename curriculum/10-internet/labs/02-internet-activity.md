---
layout: page
title: Internet Activity
unit: 10
uniturl: 10-internet
lab: 2
laburl: 02-internet-activity
---


Lab Internet Activity
===========================
This activity is a follow up of, How the Internet works. Create a single written document (such as Microsoft Word) that answers the questions below. Work by yourself or with a partner to answer these questions. 

The purpose is to try to understand something about what the Internet is and explore a few examples of how you can use computation and computational thinking in ways related to the Internet.

There are four general parts to this: a map of the internet, understanding that the Internet is a network of autonomous systems (regional networks), thinking about IP addresses and DNS --- the Domain Name System, and tracking how packets travel on the Internet.

Each of the following four sections have questions that you (and your partner, if you have one) will answer.

Map of the Internet (10-15 minutes)
-----------------------------------
First let’s look at a few examples to get the conversation started. Here’s a website that says it’s a map of the Internet: [http://internet-map.net/](http://internet-map.net/)

Click around, zoom, and in general play with this for a couple of minutes.

*Task: Mention a question or observation you have about the map. There can be more than one.*

There are other maps of the Internet.

[http://www.peer1.com/map-of-the-internet](http://www.peer1.com/map-of-the-internet)

[http://www.telegeography.com/telecom-maps/global-internet-map/](http://www.telegeography.com/telecom-maps/global-internet-map/)

[http://xkcd.com/195/](http://xkcd.com/195/)

 

Autonomous Systems (10-15 minutes)
----------------------------------
Conventionally the Internet is often referred to as a “network of networks”. A slightly different view is that the Internet is a network of autonomous systems that communicate with each other using the [Border Gateway Protocol (BGP)](http://docwiki.cisco.com/wiki/Border_Gateway_Protocol). Let’s find out something about autonomous systems in this activity.

*Task: Answer following three questions about Autonomous Systems*

 * How many autonomous systems (AS) are there today on the Internet?
 * What is the AS number of Duke University?
 * What entity/company is associated with AS 16631?

 

IP Addresses and Domain Names (10-15 minutes)
---------------------------------------------
An IP address identifies a machine/device connected to the Internet; it’s a 32- or 128-bit number, e.g., 184.84.228.110 for an IPv4 dotted-quad. People like names better than machines, names like whitehouse.gov. We’ll explore names and addresses, specifically how they tie together and how they work (briefly).

You can use [http://www.kloth.net/services/nslookup.php](http://www.kloth.net/services/nslookup.php) or [http://www.kloth.net/services/dig.php](http://www.kloth.net/services/dig.php) to answer these questions, there are other services as well that wrap dig and nslookup in a website. For geolocation of an IP address you can try [http://geomaplookup.net/](http://geomaplookup.net/) or [http://www.infosniper.net/](http://www.infosniper.net/)

*Task: Answer following four questions*

 * What is the domain name registered to 65.39.205.54?
 * What is the IP address associated with girlswhocode.com?
 * What is the IP address associated with csprinciples.org?
 * In what city is the IP address of csprinciples.org located?

 

Traceroute (10-15 minutes)
--------------------------
The traceroute command shows the “hops” that a packet will take in getting from one place on the Internet to another.  This command/tool can be run via several websites, some that offer visualizations. We’ll use [http://traceroute.org](http://traceroute.org) which maps several sites in other countries to your IP address or one you specify. For visualizing you can try either [http://traceroute.monitis.com](http://traceroute.monitis.com) or [http://www.yougetsignal.com/tools/visual-tracert/](http://www.yougetsignal.com/tools/visual-tracert/)

For example, using the pages at traceroute.org, if you start from the site given in the country of Kyrgyzstan 21 hops are shown to reach Duke (output from website)

traceroute to 152.3.250.1 (152.3.250.1), 30 hops max, 72 byte packets

1 r2d2 (212.42.96.42) 0.255 ms 0.262 ms 0.246 ms (0% loss)

2 R76 (212.42.96.80) 0.340 ms 0.310 ms 0.314 ms (0% loss)

3 195.218.197.85 (195.218.197.85) 57.587 ms 57.609 ms 74.506 ms (0% loss)

4 p4.Moscow.gldn.net (195.239.11.166) 81.353 ms 85.248 ms 83.839 ms (0% loss)

5 mx01.Stockholm.gldn.net (194.186.156.41) 75.101 ms 75.684 ms 75.102 ms (0% loss)

6 xe-11-0-0-xcr1.skt.cw.net (166.63.220.65) 75.182 ms 90.087 ms 75.216 ms (0% loss)

7 xe-0-3-1-xcr2.amd.cw.net (195.2.9.217) 201.529 ms 176.642 ms 177.156 ms (0% loss)

8 ae0-xcr2.amd.cw.net (195.2.30.105) 175.810 ms 175.820 ms 175.656 ms (0% loss)

9 xe-7-0-0-xcr2.lsw.cw.net (195.2.25.38) 176.593 ms 176.578 ms 176.607 ms (0% loss)

10 xe-2-2-0-xcr2.lnd.cw.net (195.2.28.185) 178.416 ms 175.892 ms 175.479 ms (0% loss)

11 xe-3-1-0-xcr1.bkl.cw.net (195.2.21.214) 103.025 ms 102.920 ms 103.093 ms (0% loss)

12 xe-8-1-0-xcr1.nyk.cw.net (195.2.25.26) 176.424 ms 176.293 ms 200.133 ms (0% loss)

13 nyc-brdr-02.inet.qwest.net (63.146.27.61) 174.859 ms 174.929 ms 174.798 ms (0% loss)

14 * * * (100% loss)

15 65.121.156.210 (65.121.156.210) 200.693 ms 216.372 ms 200.503 ms (0% loss)

16 rtpcrs-gw-to-wscrs-gw.ncren.net (128.109.212.9) 223.205 ms 203.419 ms 203.567 ms (0% loss)

17 rlgh7600-gw-to-rtp-crs-gw.ncren.net (128.109.9.6) 206.194 ms 206.184 ms 206.192 ms (0% loss)

18 roti-gw-to-rlgh7600-gw.ncren.net (128.109.70.18) 215.218 ms 215.790 ms 215.372 ms (0% loss)

19 tel1u-datacenter-vrf.netcom.duke.edu (152.3.234.25) 204.385 ms 204.414 ms 205.012 ms (0% loss)

20 tel2u_3_12_4.netcom.duke.edu (152.3.250.254) 215.001 ms 215.041 ms 214.813 ms (0% loss)

21 dukedns1.netcom.duke.edu (152.3.250.1) 204.437 ms 204.365 ms 204.392 ms (0% loss)



Your task is to pick 3 cities/locations from [http://traceroute.org](http://traceroute.org) and use tools to find the number of hops to either your machine (sometimes that’s the default) or to Duke’s nameserver which is 152.3.250.1 --- if you have a choice of how to connect, use traceroute. Many of the links at traceroute.org don’t work, click around as needed.

*Task: Mention the three cities/locations, you have chosen and the number of hops*

 

Reflection on these Internet Tools
----------------------------------
 * What impact has the Internet had, on solving problems and gathering information?
 * What problems has the Internet created? What are we doing to address these problems?



