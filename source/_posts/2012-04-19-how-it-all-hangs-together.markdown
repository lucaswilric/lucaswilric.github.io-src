---
layout: post
title: How it all hangs together
date: 2012-04-19 22:48:31 +1000
tags: [framework, jenkins]
---
So there's a few lumps of [code][1] [on][2] [Github][3] that are supposed to make this blog happen. But what is it that makes it all work, process-wise? How can I make this a "just commit it and it goes" kind of operation?

Well, it's basically [Jenkins][4]. Jenkins is a build manager, or, more generally speaking, a manager of automated tasks. It was originally designed for building software (that is, doing all the things that need to happen to turn source code into stuff the computer can actually understand), so it plugs into source control repositories very nicely indeed. And given that the whole idea of this blog is that it uses a source control repository for storage, that's exactly what I need.

Now, let me be honest: getting Jenkins running on Ubuntu at the latest version took me a while. I installed Hudson (Jenkins's previous incarnation) first and tried that, then got rid of it and installed Jenkins from the Ubuntu APT repository. Then I found that version was old and didn't support the plugins I wanted, so I got rid of *that* one and found the APT repository that's maintained by the folks who make Jenkins. So learn from my time-wastage: go to the [Jenkins wiki][7] and follow the "Installation" instructions (or [go here][8] and follow the *only* instructions) if you want to install Jenkins on Debian or Ubuntu.

Now, back to the fun. For me, the task that needs automating is translating my mountain of YAML templates and YAML/Markdown blog posts into HTML pages such as this one, which your browser can present nicely for you to read. I don't want to have to run that task myself each time I make a post, and then manually upload the resulting lump of HTML to the website. I want that taken care of, so I can work on more interesting things, like drinking and sleeping.

Any automated task needs to know a few things: when to start, what to do, and what should happen next. Jenkins lets you specify these things quite adequately on its Job Configuration page. In my case, I want the process to kick off whenever I commit a new post, or make a change to an existing one. So I tell Jenkins to check my Github every 5 minutes for new commits.

Now because I also make changes to my template and my build process, both of which are also on Github, I ask Jenkins to check those too. Unfortunately [getting Jenkins to check out code from more than 1 repo in a single Job is horribly difficult][9], so I have a separate Job for each repo. Then I tell Jenkins to kick off the "get the templates" task after it's finished the "get the posts" task. And after that, the "get the build process code" task.

After it's got all the code, we're ready to start building. I've made a fourth Job, and this one actually does what we're here to do: build the blog. It runs the Rake task that translates the YAML and Markdown into HTML and inserts templates in the appropriate places, and puts all the HTML into one folder. Which leads us to the next task...

Uploading to the server! I use [Amazon S3][5] to host this puppy, so [s3cmd][6] is my wingman here. It synchronises the HTML folder with the S3 bucket I've designated to hold my blog. This task could just as easily be an FTP job, or whichever other means of shifting bits takes your fancy. I just make an "Execute shell" build task that runs s3cmd with my chosen parameters. You only have to configure s3cmd once - it remembers your credentials, so you don't have to tell Jenkins.

"But hold on! Why didn't you just use the S3 plugin for Jenkins?" Well, I'm glad you asked. Sort of. Not really. But anyway, there were a couple of reasons. Firstly, I couldn't figure out how to get Jenkins to upload all the files I needed **and** preserve folder structure when uploading to S3. Second, s3cmd only changes the files that need to be changed, which may not make much of a difference now, but as the blog grows (particularly if I post lots of photos) it will become much more important.

So that's basically it. 9 paragraphs and 5 Jenkins jobs later, that's all there is to it.


[1]: http://github.com/lucaswilric/blog_posts
[2]: http://github.com/lucaswilric/blog_templates
[3]: http://github.com/lucaswilric/blog_builder
[4]: http://jenkins-ci.org
[5]: http://aws.amazon.com/s3/
[6]: http://s3tools.org/s3cmd
[7]: http://wiki.jenkins-ci.org/display/JENKINS/Installing+Jenkins+on+Ubuntu
[8]: http://aaronbonner.tumblr.com/post/8339092868/installing-jenkins-on-ubuntu
[9]: http://stackoverflow.com/questions/1808891/using-hudson-and-build-steps-with-multiple-git-repositories
