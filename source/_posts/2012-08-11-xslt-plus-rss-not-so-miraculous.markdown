---
layout: post
title: XSLT plus RSS - not so miraculous
date: 2012-08-11 12:39:17 +1000
tags: [RSS, XSLT, rendering, framework]
---
In [a previous post][1] I waxed lyrical about how great it would be to render an RSS feed in a browser by providing an XSL stylesheet telling the browser how to display it. It was working great when I tried it at home, but when I tried it at work it fell to pieces.

I still don't completely understand why. I suspect something's messing with HTTP request and response headers at work, either in the request or in the response. It works fine in Chromium at home, but not in Firefox, Chrome or IE at work. (It turns out that Google has changed the way Chrome handles feeds. Here's [Dave's thread on the subject][2].)

It also doesn't render in Dolphin Browser on my phone. I was a little bit disappointed about this, but not too surprised once I took a second to think about it. It's a mobile browser, and fancy doodads lead to bloat, and bloat is bad.

So I'll be switching back to the old &lt;link&gt; tag strategy to point to the RSS feed from index.html. That strategy, at least, is widely supported.

[1]: /2012/08/11/xslt-plus-rss-equals-the-business.html 
[2]: http://threads.scripting.com/81012ByDw/arrghChromeBrokeRssAgain
