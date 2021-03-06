---
layout: post
title: Migration
date: 2012-08-14 19:37:19 +1000
tags: [learning, amazon, dns]
---
Over the weekend I decided to get off Wordpress completely and move over to the blog I built with my own ten fingers. The next stage of the experiment is to stop making excuses by calling it an experiment. Use it as the real thing and see how far I get.

In the process of shifting from Wordpress to ... (well, there's the first big question: what am I going to call this thing?) my blog, there were a few things I tripped over. Some were more obvious than others from out there on the Internets, but I've learnt from all of them.

First up: **you can't use CNAME records on the apex of a domain**. The RFC (the protocol spec) for DNS just doesn't allow it. It turns out that before I switched, Wordpress had been taking care of this for me. Thanks Wordpress. When I got right down to what I wanted, I figured I needed a way to serve up an S3 static website from my apex domain. So I wrote a little cronjob that checks every so often and makes sure the A record is up to date for that domain. Not particularly elegant, especially if the machine running the cronjob goes down. But it gets the job done for now.

Second: one should **disable auto-posters** like Twitterfeed before messing about with the location and content of one's RSS feeds. Mostly I left this just because I didn't think it mattered, or that anyone would notice. But a couple of people did point it out to me and that was kind of embarrassing, even if there were no dire consequences.

Now I knew this before, but I have to preach: I *really* love how easy **S3 static websites** are. Don't get me wrong, if Amazon screws me I'll be switching to something else - that's the entire point of making a blogging tool that publishes static text. But in the meantime I can set up a new website in 5 minutes and get more reliable storage, better uptime and faster page loads than I'll ever get running my own server.

Amazon's DNS product **Route53** is also handy, particularly because changes propagate quickly. It lets me iterate fast and get things working more quickly, even though I was kind of flailing for a bit.

**DNS** itself is also pretty awesome, especially the CNAME, and particularly with fast propagation. It goes "What's that? You want to change your website from one platform to another, and then back again? Sure, that's easy! Now watch while I make you lunch!" I'm pretty seriously in awe of anyone involved with the development of DNS and protocols like it - simple things that are just so damned powerful and widely applicable. Hats off.

My appreciation for **Bootstrap** is growing too. In particular, it gives me a non-awful starting point for website designs, and some pre-laid groundwork so I can iterate quickly. Once I decided what I wanted at [lucasrichter.id.au][1], I got something together in a very short time - the text took me longer than the layout. And it's six dozen times better than anything I would've made from scratch, even if I'd taken ten times as long.

[1]: http://lucasrichter.id.au/