---
layout: post
title: MacBook charging woes (solved-ish)
date: 2013-06-23 09:38:32 +1000
tags: [macbook, battery, temperature]
---
I had an interesting and slightly scary time with my MacBook Air this morning. Basically, it wouldn't start. I first noticed it last night, and thought the battery was flat. This turned out to be correct. I popped it on to charge overnight. I noticed that the "charge" light never went orange to indicate charging, but stayed green. I thought nothing of it until this morning when I took the machine off the power adapter, went to turn it on, and it still wouldn't start.

I'm taking my machine overseas for an extended period in a few days. This is *not* the time for it to start having issues.

Now the temperature in Melbourne at the minute is about 3.5<sup>o</sup>C (which on the Aussie thermometer is *really bloody cold*). It turns out that [the MacBook power adapter doesn't really like cold temperatures](http://apple.stackexchange.com/a/55256/19695), but I'm not sure whether that was the problem, because when I connected the power adapter and turned it on, the machine booted. That said, all was not well at that point. The battery icon still said "Battery Is Not Charging", which changed to the normal "charging" message after a few minutes. So I started thinking that the battery might be the issue.

A quick search suggests that [lithium ion batteries should be fine under subzero conditions](http://www.physicsforums.com/showthread.php?t=345524), so I'm guessing one of two things is true:

* The battery isn't the problem (i.e. it's probably the power adapter, which has documented problems with low temperatures)
* The MacBook Air doesn't use a lithium ion battery (research suggests it has some kind of "advanced battery technology"), but some other kind which doesn't like near-freezing temperatures.

The former possibility seems more likely to me. So then the question is: if the power adapter was having trouble, how come I could turn the machine on in the first place? I'm thinking that powering the laptop *without* charging drew a low enough voltage that the cold power adapter could handle it. The flow of current made the adapter warm up to a point where it could supply enough volts to charge the battery. Et voila, I have a charging laptop.