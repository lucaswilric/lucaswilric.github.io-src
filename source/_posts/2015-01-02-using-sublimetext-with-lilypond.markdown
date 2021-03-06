---
layout: post
title: Using SublimeText with Lilypond
date: 2015-01-02 12:23:55 +1000
tags:
  - Lilypond
  - Sublime Text 3
  - Music
---
I've spent a little time recently working on my Lilypond workflow, trying to improve on the process I used when I was arranging a moderately long and complex work last year. I used a tedious process involving hand coding (in Vim, until I decided learning both Vim and Lilypond at the same time was a bad plan), running Lilypond in a terminal, then checking the output in Preview (OSX's built in PDF viewer).

Once I started using [Sublime Text](http://www.sublimetext.com/), I got much faster, but the feedback cycle (edit, switch to Terminal, run Lilypond, switch to Preview, check result) was still a killer. So I started using a Makefile that a mate had put together, along with Sublime's build functionality. So now I create a PDF by hitting &#8984;-B (or Ctrl-B in Windows) or F7. That saves a little time.

Little did I realise that the [SubLilyPond plugin](https://github.com/yrammos/SubLilyPond) contains a build system for creating Lilypond PDFs. SubLilyPond is pretty great even without that; it does syntax highlighting for Lilypond files. There's some talk in the README about snippets coming up in future, and I'm looking forward to that.

Meanwhile, though, it's not a bad idea to create your own Lilypond snippets, especially for layouts or instrumentations that you use frequently. [Creating Sublime snippets is pretty easy](http://docs.sublimetext.info/en/latest/extensibility/snippets.html) - I learned how to do it the other day. The next day, it made the difference between writing down a little musical idea I had, and forgetting it forever.

Friends have recommended [Frescobaldi](http://www.frescobaldi.org/index.html) as a graphical alternative to all that hand coding. I haven't been able to get it working after installing it with Homebrew, and if it doesn't work when I install it with a package manager, I'm not going to sink much time into fixing it by hand. And anyway, one of the things I like most about Lilypond is the fact that the file format is plain text. Programmers have developed some great tools for working with plain text over the years (version control, anyone?), and given that I know how to use a few of them, it seems silly not to. Plus, I just love crafting stuff by hand like this, at least as long as it's a hobby with few deadlines.

Next, I'd like to get the PDF side by side with the code. Preview updates automatically when you change the file, so that's taken care of. Mostly I think I just need a bigger (another?) screen for this whole thing to work best.