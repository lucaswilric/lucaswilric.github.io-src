--- 
layout: post
date: 2009-12-26 11:36:31
title: LiveCD trouble with Ubuntu 9.10 (Karmic Koala)
tags: 
- karmic koala
- linux
- livecd
- Ruminations
- ubuntu
---
  <p>
  
  I replaced the guts of my machine recently (motherboard, CPU, RAM, video) and, having done this, my Ubuntu Intrepid install wouldn't work, because the kernel didn't support the new hardware. So I decided I'd install the latest version (9.10, Karmic Koala) to get a more recent kernel, and hopefully some other goodies. Downloaded the LiveCD on my laptop, burnt a disk, slipped it in the drive, and off we went.
  
  </p>
  
  <p>
  
  Presented with the typical startup screen, I chose to Install Ubuntu. But partway through the boot process, I was presented with a message to  the effect that there wasn't anything to boot. I think the exact words were <q>Unable to find live filesystem to boot.</q> I googled and struggled for a few hours, and then thought of something.
  
  </p>
  
  <p>
  
  My motherboard has a legacy IDE interface, which both my hard drive and my DVD drive are currently plugged into (having replaced everything else, my funds didn't stretch so far as replacing those). It turns out that the LiveCD doesn't do so well at noticing bootable images on the IDE interface.
  
  </p>
  
  <p>
  
  What did I do? I plugged in a USB DVD drive I had lying around. Worked like a charm, after I fiddled around in BIOS to make sure of the boot order.
  
  </p>
  
  <p>
  
  The moral of the story is: well, I don't quite know. But probably something like "don't assume any one thing is working correctly."
  
  </p>
  
