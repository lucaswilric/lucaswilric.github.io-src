---
layout: post
title: Doing text searches on print music
date: 2008-12-01 11:39:16 +1000
tags: [Google, lyrics, OCR, print, music, scan, search, Tracker]
---
I've been playing around with <a href="http://projects.gnome.org/tracker/">Tracker</a> (the Linux text search tool) this morning, because I've just received a bunch of sheet music in PDF form, and I wanted to be able to search for songs. And the file naming system used by the providers of these PDFs sucks major arse. So using Tracker to index the songs so I can search for them by title (and, incidentally, lyrics) seemed like a pretty logical thing to do.

But I want more. I want to be able to do this for my hard-copy music as well.

My singing teacher does something like this. He has a dirty great spreadsheet with all the names and composers of all the sheet music he owns (as of the last time it was updated), to which he refers when he wants to find something. This seems very kludgy to me, mostly because he refers to the hard copy. And that takes up nearly a ream of A4 paper.

So how can I get all that metadata into my PC without having to type it all in? Excessive scanning is also out because I'm too lazy.

The solution in my mind at the moment is scanning just the metadata: the title of the song, the composer and show/opera if they're there, and the book and page on which it appears. In short, the contents page of any given music book. If I scan and OCR those to a sufficient degree of accuracy, I should be able to find what I'm looking for (assuming I have it). Especially if I can scan it into PDF format with the OCR text included. That way, the original image is still there for me to read, even if the computer can't. So if I'm looking for the song <em>Piano Man</em>, but the OCR hasn't recognised it, I can search for something like <em>Billy Joel</em> and eyeball the results. Less efficient, to be sure, but it's only a backup option.

Now obviously this approach doesn't work so well for searching on lyrics. For that to work, I'd need to scan every page of music I own, and that just doesn't scale. The only alternative would be to get access to an existing repository of song lyrics, and get the title from there. Now, where would I find such a repository?

Wait a minute... **the Internet!**

Here's a brief, half-baked outline:

1. Search Google (or a more music-specific resource) for the lyrics in question
2. Grab the song title from the results. How, I don't know just yet, but &lt;title&gt; tags seem like a likely option.
3. Search on my PC using Tracker for the title I've found.
4. ???
5. **Profit!**

One more idea for the pile.
