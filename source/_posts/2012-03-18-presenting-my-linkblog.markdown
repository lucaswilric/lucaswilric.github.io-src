--- 
layout: post
date: 2012-03-18 17:24:00 +1000
title: Presenting my linkblog
tags: 
- grabbit
- linkblog
- software
---
With some small trepidation, I present to you a couple of items. 

Firstly, <a href="http://links.lucasrichter.id.au/">my linkblog</a>, in which I point to internet objects of all sorts which I have found interesting, amusing, informative, scary or otherwise worth reading.

Secondly, <a href="http://github.com/lucaswilric/grabbit/">Grabbit</a>, the web application I have made which runs the aforementioned linkblog. It also forms the centre of a couple of other useful RSS-related applications I use.

I'm a little bit excited about this app, particularly this iteration, because it has shown itself to have uses beyond what I originally anticipated. To me, that's a shadow on the wall that signals the possibility of versatility and enduring usefulness.

Grabbit is an application which consumes <a href="http://www.whatisrss.com/" title="What is RSS?">RSS</a> feeds, then stores the links in each feed for use by some other app. Each feed subscription can have text tags attached to it, and each item that is created will automatically have the same tags as the subscription it came from.

Here's one way you can use it: you subscribe to several feeds using Grabbit (just give Grabbit the address of the feed and a couple of other details) and tag them all as 'podcast'. Then run a script that makes a request to Grabbit, asking for all items tagged 'podcast'. That script might then download all the URLs it receives onto your mp3 player, ready for you to listen to.

Please go and have a look at the source code if that kind of thing interests you. Then fork it and have a play. I'd be happy to hear what you think.
