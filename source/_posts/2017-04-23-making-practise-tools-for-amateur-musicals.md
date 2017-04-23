---
layout: post
title: Making practise tools for amateur musicals
date: 2017-04-23 11:40:00 +1000
tags: [music, software]
---
Last year I served as the Musical Director for a local musical theatre production. My duties involved teaching the music to the cast so that they could perform from memory on stage, including harmony singing in up to 4 parts.

Because the community group I work with (the [Diamond Valley Singers](http://dvsingers.org/)) has a policy of not auditioning the chorus for our shows, we get people of all skill levels joining the cast. Some people have already developed the skills they need to learn the music and sing in parts from memory, while acting and dancing at the same time. Others haven't, and need as much help as the creative team con provide to get them ready for performance. So I spent quite a lot of time preparing materials to help people practise, including more readable scores and practise backings for all the vocal parts.

Here's a little run-down of the tools I used to put these materials together. All the software is free, or comes packaged with Mac OSX. Hardware is another story, but investing in even a modest MIDI keyboard made a huge difference to the amount of effort required to get everything done.

# MuseScore

[MuseScore](https://musescore.org/) is an open source music editor, which has all the same basic features as Sibelius. More advanced features such as music scanning are not included, but the price is right, particularly for an amateur like me. The vital features for me were:

* Input from a MIDI keyboard. This speeds up input in a huge way, especially as scanning wasn't an option. I used an [M-Audio KeyStation 49](http://www.m-audio.com/products/view/keystation-49), which was exactly the right size for my desk, and connects easily via USB.
* WYSIWYG (What You See Is What You Get) score editing. Believe it or not, not every music editing program has this feature (I'm looking at you, [Lilypond](http://lilypond.org/)).
* Plain-text output in an open format (MusicXML). This was an important feature for me because I wanted to use the programming tools I know and love, to help me with things like version control (which I'll go into more later). MusicXML is not MuseScore's default format, but it beats the pants off any binary format for my purposes.
* Pretty good help from the community. After consulting Google, I was able to get solutions to quite a few problems from the MuseScore [user forums](https://musescore.org/en/forum).
* Finally, PDF and MIDI exports. This allowed me to turn the scores I was working on into backings for the practise recordings. I could also be certain that those backings would match the score exactly. Again, a pretty standard feature for this kind of software, but I mention it because it was especially important for this project.

# Git

I'm a software engineer by profession, and I like to apply programming tools to my other pursuits because I know how to use them, and they help me approach problems in ways I understand. I used Git to version control my scores, so I knew that if I completely messed things up, I could always revert to a previously saved version. At the end of the process, I also got a nice little story created by the sequence of commit messages I'd written. Some day, a musical archaeologist will be able to follow my creative process step by step, because of those records.

I should point out that I only used Git's most basic features. I did most of my work on a single branch, and didn't do any merging at all. Change tracking and save points were all I needed in this case. Git has some great features to help with integrating changes amongst a team, but I had no need for them this time, as I was the only one contributing.

Using Git was only practical because I could get MuseScore to output my work in a plain text format, in this case MusicXML. It's very hard to do version control in a space-efficient way for binary files, as it's a lot easier to compress plain-text files. Even if plain-text files are less space efficient individually, they compress much better in large numbers.

# Tascam stereo recorder

Once I had my scores and backings done, I was ready to record voice parts. I dubbed these over the top of the backings to help my singers practise, since as I mentioned, I was working with singers of all skill levels. I used a Tascam portable stereo recorder mounted on a tripod to record the parts, singing the bass and tenor parts myself and calling in a couple of friends to help me with the soprano and alto parts.

# Audacity

The one thing that wasn't ideal for me about the Tascam recorder was that I
couldn't figure out how to record at a decent volume. Even though my singing voice is quite loud and I was standing right in front of the recorder, the resulting file was *very* quiet. I suspect it's because the microphones can handle very loud sounds (e.g. a symphony orchestra playing fortissimo), and even my loud voice is quiet by comparison. Anyway, I used [Audacity](http://www.audacityteam.org/) to amplify the raw audio files before I combined them with other sounds.

# GarageBand

Once all the parts were recorded and amplified, I used Apple's GarageBand to mix everything together. With GarageBand I was able to prepare instruments-only tracks for more confident singers, tracks with individual parts for the less confident, and also tracks with all the parts included, which turned out to be very helpful during choreography rehearsals.

GarageBand is an entry level tool as far as recording goes, but I didn't need anything more sophisticated for this project. Just decent MIDI sounds, some chopping and swapping of recorded samples, and basic mixing tools.

# Adjusting tempos

As we approached the end of the rehearsal process, I found I needed to adjust some tempos to be more suitable for the venue and the choreography. Rather than going back and re-recording everything at a different tempo, I was able to use Audacity's "Change Tempo" feature (under the Effects menu) to speed up and slow down songs (or parts of songs) as required. You do need to be pretty accurate with your selection if you only want to adjust part of the song, but the UI for this feature is surprisingly functional considering Audacity's otherwise unattractive interface. I say this because it does the sums for you; you tell it what speed it is now and what speed you want it to be, and it figures out the percentage to adjust by. Exactly the kind of thing that computers do more easily than humans.

So those are the tools in my practise materials toolbox. I hope you've come across something new here, or been reminded of something you already knew.

Happy arranging!

