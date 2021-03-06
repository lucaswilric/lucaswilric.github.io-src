---
layout: post
title: An advance in templating technology
date: 2012-04-12 11:12:11 +1000
tags: templates framework old-blog-builder
---
 There are a few challenges in developing a templating engine, and I think I've solved one of them for this framework: including templates inside other templates.
 
 To include another template, you use something like the following syntax:
 
 <code>&lt;%= template_name( yaml: or, ruby: hash, to: be, passed: to, the: template ) %&gt;</code>
 
 You might be able to tell just by looking at it, but I'll explain anyway: that there is an ERB block (similar things are found in PHP and ASP, both Classic and .NET), which prints the result of the Ruby expression between the <code>&lt;%</code> and <code>%&gt;</code> brackets. The <code>=</code> is what tells the interpreter to print instead of just executing the code. The template name is called as a function, which is received along with the hash as an argument to the call to <code>method_missing</code> which will happen because the class doing the interpreting has no method with that name. As a result, templates or hash keys that are the same as Ruby reserved words or method namess of the <code>Object</code> class won't work.
 
 This is a little bit more 'code-y' than I would have liked, but if you look through the history of this post you'll see that on my previous attempt I tried to roll my own templating language. That emphatically failed to work well - it simply wouldn't extend to do the things I wanted to do. So after much head banging and head scratching I decided to use ERB instead.
  
 You can see it all in action [here](/posts/burnie-by-night.html) (remember to click on the "Source" link at the bottom) - a template call is used to insert the photo.
 
