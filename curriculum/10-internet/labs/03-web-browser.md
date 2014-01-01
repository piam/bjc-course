---
layout: page
title: Internet Activity
unit: 10
uniturl: 10-internet
lab: 3
laburl: 03-web-browser
---

How A Web Broswer Works
=====
Have you ever wondered how a web browser works? Well, let's find out.

HTML Source
----

You are currenlty looking at this page using a web browser, most likely Chrome or Firefox. Both of these browsers have the option to show you the source code of the web page, i.e. the instructions that are given to your browser in order to render the page. Under Firefox and Chrome, you right click on the page and a menu appears. Choose View Page Source. 

Go ahead and do it now. 

Now you see the HTML source code of this page. This is what a browser interprets to render the web page you are viewing. Without going into further detail of how HTML works, let's get into the more technical details of how to get to this source code. 

Telnet
----
Web Browsers do basically three things: They connect to a server, request a page (as specified in the URL of the address bar) and then show the content that is returned. The content, as we have seen in the last paragraph, is encoded in HTML which is then interpreted and rendered to the screen. What we want to concentrate in this part of the lab is the connection and the page request. 

A simple connection can be established with the Linux program telnet. The program telnet basically sends the keyboard input to the remote host as if one was typing directly on the remote machine and then sends the remote screen output (only text) back at the local host. Let's watch a historical introduction to the program from 1995 (which is now pretty amusing, especially in the end): Video here.

So now, about 20 years later, how different is the Internet now? Let's use telnet and find out. Note, telnet might not be available under the default installation on Windows.

If you look into the address bar of your browser now, you will find a URL which points to it. The URL starts with http://inst.eecs.berkeley.edu which specifis the protocol (http://) and the server. After that, the URL contains a file path on the server.
So lets instruct telnet to connect to http://inst.eecs.berkeley.edu and grab this web page.  Telnet does not know of http:// (which stands for hypertext transfer protocol) since it's essentially a copy program. Instead, we need to instruct telnet to connect to port 80, which is the default port for http. Enter the following:

telnet inst.eecs.berkeley.edu 80

You should now see a response that looks like this:

```
Trying 128.32.42.199...
Connected to inst.eecs.berkeley.edu.
Escape character is '^]'.
```

with a blinking cursor below. Congratulations! You just established a connection to the institute's web server!

Now all you have to do is instruct the webserver to fetch the website. Since telnet does not know about http, we need to speak the protocol ourselves. the command for getting a webpage is GET followed by a path. Let's try it, enter the following: 

`GET /`

You should now see a response that looks like this

```
...]
   377 378 Cory Hall, 333 Soda Hall
    University of California
    Berkeley  CA  94720-1770
    </DIV>
  </td>
</tr>
</table>
<HR>
<!--#include virtual="tail.html"-->

</BODY>
</HTML>
`Connection closed by foreign host.
```

Congratulations, you just downloaded the page for http://inst.eecs.berkeley.edu/! 

Now-
Download the webpage that you are currnelty looking at (this page).
Take a moment to discuss with your peers the technical changes between the historical video and today.
 
Again, after all this work: Let's finish with another fun one. Enter-

   *telnet towel.blinkenlights.nl*

Don't watch to the end though, it's long!
