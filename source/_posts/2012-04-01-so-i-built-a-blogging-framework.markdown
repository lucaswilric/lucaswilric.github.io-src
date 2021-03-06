---
layout: post
title: So I built a blogging framework...
date: 2012-04-01 23:42:25 +1000
tags: [framework]
---
I wrote a post a little while ago about the concept of a [blog that uses a version control system (VCS) for storage](http://lucasrichter.id.au/2012/02/13/building-a-blog-atop-a-version-control-platform/) instead of a relational database, and the benefits that might have.

This is me, trying that idea out. This blog, new and unpolished as it is, has no relational database in the back. Instead, it uses Git for storage, so you can view the source for it on my Github ([posts](https://github.com/lucaswilric/blog_posts)) ([templates](https://github.com/lucaswilric/blog_templates)) ([Rake tasks](https://github.com/lucaswilric/blog_builder)).

I write posts in [Markdown](http://en.wikipedia.org/wiki/Markdown), which I then encapsulate in a [YAML](http://en.wikipedia.org/wiki/YAML) document so I can store some metadata. Then it's all "compiled" into static HTML by [Rake](http://en.wikipedia.org/wiki/Rake_%28software%29), and I deploy the results to a server such as the one you're reading this on now.

It's by no means anything-but-nerd friendly, but I'm a nerd so that's OK. And tools can be written later, if necessary, to abstract all the nerdy stuff away :)

I've learnt a lot in the few days I've been working on this. A lot about Rake, a bit about YAML and Markdown, and at least the basics of [Jenkins](http://jenkins-ci.org), the build server I'll use to run the whole thing in the background when it doesn't need quite so much attention.

There are a few pain points (previewing my posts, for one), but they'll be ironed out in time. Or I'll just stop using this and stick with Wordpress. Whatever. Failure is absolutely an option here.

You can view the source for this post at https://github.com/lucaswilric/blog_posts/blob/master/so-i-built-a-blogging-framework.yml

*EDIT (27/8/2016): You may think this framework I'm describing is a lot like [Jekyll](https://jekyllrb.com/), and that's because it is. I'm actually switching the blog over to Jekyll today, because I lost enthusiasm for maintaining my own framework, and Jekyll does basically the same thing, only much, much better.*