---
layout: post
title: Testing the build and deploy goodness...
date: 2012-04-02 21:54:12 +1000
tags: [test]
---
If I'm right, then all I have to do is save this file and push it to Github, and then by some Jenkins-y magic it will appear on the blog!

Ain't that lovely?

Today's work has been wrestling with Jenkins. First finding out that the version I had didn't support the plugins I wanted, then upgrading Jenkins and dealing with some dodgy default plugins breaking my build, then finding out that the S3 plugin didn't do what I wanted anyway. :\

But then I found an excellent little command line tool called [s3cmd](http://manpages.ubuntu.com/manpages/intrepid/man1/s3cmd.1.html). Its **sync** option does exactly what I need: upload all the files in a folder *and* actually keep the folders, rather than flattening out the hierarchy like the S3 Jenkins plugin does.

So now (in theory) I shouldn't need to touch Jenkins at all while I'm away on holiday!
