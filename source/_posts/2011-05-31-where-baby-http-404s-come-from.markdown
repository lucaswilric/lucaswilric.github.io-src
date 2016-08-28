--- 
layout: post
date: 2011-05-31 17:22:38 +1000
title: Where baby HTTP 404s come from
---
DISCLAIMER: I maintain the code that I refer to in this post, but I didn't <em>write</em> the code.

I've been hunting HTTP 404 errors (that's the "File Not Found" variety), and today I came across a bit of a puzzler. The non-existent image files were being referred to by a stylesheet as part of a CSS `background:` instruction, but the rule that contained the instruction was never invoked. That is, the rule was for a class name that was never used.

How the hell was I getting these image requests if the code that started the requests was never being used?

Then I noticed that the errors were coming from just a few different user agents. And they all had something about them...

* LG-GW305/V100 Obigo/WAP2.0 Profile/MIDP-2.1 Configuration/CLDC-1.1 UNTRUSTED/1.0 lg-gw305
* Nokia2730c-1/2.0 (10.47) Profile/MIDP-2.1 Configuration/CLDC-1.1 nokia2730c-1/UC Browser7.7.1.88/70/352
* Nokia5130c-2/2.0 (07.95) Profile/MIDP-2.1 Configuration/CLDC-1.1 nokia5130c-2/UC Browser7.6.1.82/70/352 UNTRUSTED/1.0
* Nokia5330-1d/5.0 (06.85) Profile/MIDP-2.1 Configuration/CLDC-1.1 nokia5330-1d
* Nokia5530/UC Browser7.6.1.82/50/352
* Nokia5800 XpressMusic/UC Browser7.7.1.88/50/352
* NokiaC3-00/5.0 (04.45) Profile/MIDP-2.1 Configuration/CLDC-1.1 nokiac3-00/UC Browser7.7.1.88/69/352 UNTRUSTED/1.0
* NokiaC3-00/5.0 (04.45) Profile/MIDP-2.1 Configuration/CLDC-1.1 Opera/9.60 (J2ME/MIDP;Opera Mini/4.2.13337Mod.by.CHIZZY/503; U; en)Presto/2.2.0 UNTRUSTED/1.0
* NokiaC3-00/5.0 (04.60) Profile/MIDP-2.1 Configuration/CLDC-1.1 nokiac3-00 UNTRUSTED/1.0
* NokiaC3-00/5.0 (07.20) Profile/MIDP-2.1 Configuration/CLDC-1.1 nokiac3-00 UNTRUSTED/1.0

See it? That's right, they all come from mobile browsers. This puzzled me a bit, until I realised that it might be something you'd do to speed up the user experience if you knew they'd be on a slow connection (and you didn't care if they downloaded heaps of data they didn't need).

So here's the piece of knowledge I want to add to the internet (he said, arrogantly assuming it wasn't there already): **Mobile browsers prefetch images from stylesheets as an optimisation in the face of low speed connections.**

You're welcome.
