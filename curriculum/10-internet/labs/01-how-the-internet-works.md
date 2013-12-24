---
layout: page
title: How the Internet Works
unit: 10
uniturl: 10-internet
lab: 1
laburl: 01-how-the-internet-works
---


Lab- How the Internet Works
===========================
* Key Concept: The Internet is a network of autonomous systems.

Learning Objectives
-------------------
This task addresses the following CS Principles Learning Objectives:

 * 2. The student can explain the abstractions in the Internet and how the Internet functions.
 * 2a. Explanation of how the Internet connects devices and networks all over the world.
 * 2b. Explanation of how the Internet and the systems built on it facilitate collaboration.
 * 2c. Description of evolving standards that the Internet is built on, including those for addresses and names.
 * 2d. Identification of abstractions in the Internet and how the Internet functions.

Let's Watch the Internet
------------------------
[CNET](http://reviews.cnet.com/internet-speed-test/) provides a tool that measures the bandwidth of your Internet connection. [Bandwidth](http://en.wikipedia.org/wiki/Bandwidth_%28computing%29) is the amount of data that can be transferred over your connection per unit time. It is usually measured in kilobits per second (Kbps), thousands of bits per second, or Megabits per second (Mbps), millions of bits per second.

[Akamai](http://en.wikipedia.org/wiki/Akamai_Technologies) provides some nice [visualization tools](http://www.akamai.com/html/technology/visualizing_akamai.html).

There are a couple of command-line tools that we can use to watch packets traveling on the Internet. But first you have to find the command line on your system:

 * Find the Terminal or console program on your workstations. 
 * (Linux Users: Look under System) 
 * (Mac Users: Open Applications &lt; Utilities &lt; Terminal) 
 * (Windows User: Open the Command Prompt)

[Traceroute](http://en.wikipedia.org/wiki/Traceroute) is a network diagnostic tool that lets you display the path that your packets take across the Internet. (On Windows system, use [tracert](http://ccie-or-null.net/2011/08/30/the-different-between-tracert-and-traceroute/) instead)

$ traceroute google.com

traceroute: Warning: google.com has multiple addresses; using 74.125.224.163

traceroute to google.com (74.125.224.163), 64 hops max, 52 byte packets

 1  192.168.1.1 (192.168.1.1)  1.302 ms  0.919 ms  0.757 ms

 2  10.4.144.1 (10.4.144.1)  8.513 ms  9.206 ms  8.140 ms

 3  68.9.8.225 (68.9.8.225)  10.512 ms  10.055 ms  9.773 ms

 4  ip68-9-7-65.ri.ri.cox.net (68.9.7.65)  11.274 ms  10.933 ms  11.802 ms

 5  ip98-190-33-42.ri.ri.cox.net (98.190.33.42)  9.947 ms  9.830 ms  10.313 ms

 6  ip98-190-33-21.ri.ri.cox.net (98.190.33.21)  13.648 ms  12.782 ms  11.729 ms

 7  provdsrj01-ae3.0.rd.ri.cox.net (98.190.33.20)  11.678 ms  12.195 ms  11.936 ms

 8  nyrkbprj01-ae2.0.rd.ny.cox.net (68.1.1.173)  17.775 ms  17.548 ms  17.816 ms

 9  209.85.248.178 (209.85.248.178)  21.314 ms  17.731 ms  22.360 ms

10  209.85.251.88 (209.85.251.88)  18.121 ms  21.036 ms  18.488 ms

11  209.85.249.11 (209.85.249.11)  28.026 ms  55.017 ms  28.288 ms

12  66.249.95.149 (66.249.95.149)  39.955 ms  38.041 ms  50.290 ms

13  72.14.233.86 (72.14.233.86)  56.257 ms  65.504 ms  54.386 ms

14  64.233.174.142 (64.233.174.142)  98.997 ms  91.343 ms  89.584 ms

15  64.233.174.189 (64.233.174.189)  90.320 ms  89.137 ms  168.799 ms

16  72.14.236.11 (72.14.236.11)  90.281 ms  92.398 ms  100.019 ms

17  lax02s01-in-f3.1e100.net (74.125.224.163)  91.074 ms  99.050 ms  92.037 ms

$

[Ping](http://en.wikipedia.org/wiki/Ping) is a utility to test whether a host on the Internet is reachable: that lets you display the path that your packets take across the Internet and ti reports the round-trip time for messages to that host.

$ ping google.com

PING google.com (74.125.239.14): 56 data bytes

64 bytes from 74.125.239.14: icmp_seq=0 ttl=48 time=91.242 ms

64 bytes from 74.125.239.14: icmp_seq=1 ttl=48 time=89.957 ms

64 bytes from 74.125.239.14: icmp_seq=2 ttl=48 time=91.471 ms

64 bytes from 74.125.239.14: icmp_seq=3 ttl=48 time=90.506 ms

64 bytes from 74.125.239.14: icmp_seq=4 ttl=48 time=91.070 ms

...

Internet Infrastructure
-----------------------
The Internet is a network of independent networks -- independent in the sense that the local networks use [different protocols](http://docwiki.cisco.com/wiki/Introduction_to_LAN_Protocols) to transmit data among their computers.

Routers running the [Internet Protocol (IP)](http://en.wikipedia.org/wiki/Internet_Protocol) connect the different local networks together, creating the Internet. The IP takes care of routing data through the Internet and translates data from a local protocol (such as Ethernet) to IP and vice versa.

**Analogy**: You can think of the local networks as different countries where the citizens are connected by different languages. The IP is like a translator that translates from French to English.

Example
-------
Suppose you type the URL of your school’s home page into your browser. It may seem like your browser (the client) is directly connected to the web page (on the server), as in the top half of the [following diagram](http://en.wikipedia.org/wiki/File:IP_stack_connections.svg).

But your request and the server's response travel through several Internet abstraction layers as shown in the bottom half of this diagram.




Tracing the Data Flow
---------------------
At the **application layer**:

 * Your browser uses the [HyperText Transfer Protocol (HTTP)](http://en.wikipedia.org/wiki/Hypertext_Transfer_Protocol) protocol, the primary World Wide Web (WWW) protocol.
 * The HTTP protocol requests a translation of the host name portion of the URL - www.cs.trincoll.edu, into [IP Address](http://turing.cs.trincoll.edu/~ram/cpsc110/inclass/internet/) of the server that stores the home page, from a [Domain Name System (DNS)](http://en.wikipedia.org/wiki/Domain_Name_System) server.

There are many other application layer protocols, including:
 * [File Transfer Protocol (FTP)](http://en.wikipedia.org/wiki/File_Transfer_Protocol)
 * [Simple Mail Transfer Protocol (SMTP)](http://en.wikipedia.org/wiki/Simple_Mail_Transfer_Protocol)
 * [Post Office Protocol](http://en.wikipedia.org/wiki/Post_Office_Protocol)
 * [Secure Shell](http://en.wikipedia.org/wiki/Secure_Shell) -- remote terminal sessions

At the **transport layer**:

 * The [Transmission Control Protocol (TCP)](http://en.wikipedia.org/wiki/Transmission_Control_Protocol) ensures a reliable, ordered delivery of a stream of data, from your browser to the trincoll.edu server.

At the **internet layer**:

 * The [Internet Protocol (IP)](http://turing.cs.trincoll.edu/~ram/cpsc110/inclass/internet/) transmits 1500 byte packets of data through the internet. Each packet is sent separately from the client to the server.

At the link layer, the **hardware layer**.

Various protocols are used to transmit data across different local area networks. Some of the protocols are:
 * [Ethernet](http://en.wikipedia.org/wiki/Transmission_Control_Protocol)
 * [Digital Subscriber Line (DSL)](http://en.wikipedia.org/wiki/Digital_subscriber_line)
 * [Point-to-Point (PPP)](http://en.wikipedia.org/wiki/Point-to-Point_Protocol)




Packet Switching
----------------
The Internet (implemented by Internet Protocol) is based on [packet switching](http://en.wikipedia.org/wiki/Packet_Switching). Data is broken into 1500 byte blocks (8 bits per byte), which are transmitted from router to router through the Internet.

This contrasts with **circuit switching**, the technology that land-line telephones used to use, in which a continuous circuit was set up through switches from one end of the call to the other.

IP Addresses
------------
An [IPv4 address](http://en.wikipedia.org/wiki/IP_address) uses a 32-bit IP address, broken into 4 8-bit segments each represented by a decimal number. An IPv6 address uses a 128-bit address, broken into 8 16-bit segments represented as Hexadecimal numbers.

**Question**: Why do you think Hexadecimal representation is used in IPv6 instead of decimal?

Domain Names
------------

An Internet domain name is organized into a number of levels as shown in [this diagram](http://en.wikipedia.org/wiki/Domain_name). A domain name takes the following form:

     fourth-level-domain  .  third-level-domain  .  second-level-domain    .   top-level domain 

           turing         .         cs           .       trincoll          .         edu

A hostname is a domain name that is associated with an IP address. For example, the following are examples of hostnames:

 * trincoll.edu
 * www.trincoll.edu
 * turing.cs.trincoll.edu

But top-level domain names, such as com and edu are not hostnames.

Domain Name Service
-------------------
Domain names are mapped into IP address by the [Domain Name System](http://en.wikipedia.org/wiki/Domain_Name_System), a network of servers that keep track of the mappings.

In this example, three look-ups are need before the IP address is resolved.

 

The World Wide Web
------------------
The World Wide Web (WWW) is not a network -- technically speaking. It is a system of interlinked [hypertext documents](http://turing.cs.trincoll.edu/~ram/cpsc110/inclass/internet/) that can be accessed via the Internet.

The Web is a service governed by the [HyperText Transfer Protocol (HTTP)](http://en.wikipedia.org/wiki/Hypertext_Transfer_Protocol) protocol.

It was invented by [Sir Tim Berners-Lee](http://en.wikipedia.org/wiki/Tim_Berners-Lee), who, to his credit, turned his invention into an open standard.

"I just had to take the hypertext idea and connect it to the
Transmission Control Protocol and domain name system ideas
and ta-da! the World Wide Web."


Discussion Questions
--------------------
 * Would the Web be the success that it is if Berners-Lee had made it a proprietary system?
 * Would the Internet be the success that it is if it was not based on open standards?


