--- 
layout: post
date: 2012-02-13 06:26:33 +1100
title: Building a blog atop a version control platform
tags: 
- blogging
- relational db
- vcs
- version control
---
Most blogging platforms are database-backed: they run with a relational database storing all your posts, and then query the database when it needs to present a post on a web page. You create posts by making `INSERT` commands, and edit with `UPDATE`s.

This model has some great aspects: it's pretty fast (though not the fastest), it allows many users to run blogs on the one server (by adding a foreign key named `blog_id` to the `posts` table, for example), and it's easy to query and search, just by using SQL (the web app you're using to run your blog generally takes care of that for you). You can blog from anywhere, as long has you have a web browser.

But there are some weaknesses to this setup as well. For example, it's hard to track changes (resulting in paragraphs at the end of posts starting with **UPDATE:** or **EDIT:**). And unless you work directly on the server (which is risky), you'll have to use that web app to write your posts. Not a huge burden, unless you happen to be on dialup, or spotty 3G. It's also hard to back up.

So how do we get around these problems, without getting rid of *too* many of the advantages that a web app-based blog gives us?

Of course, I wouldn't be writing this if I didn't think I had an answer.

A Version Control System (VCS) is a tool often used by programmers to keep track of the changes they make their code. If I introduce a bug to my code (it happens), then I can use my VCS to revert to the version of the code that didn't contain the bug, and give it another shot. Or if somebody else introduces a bug, I can use the VCS we both use to find out who they are, and ... umm... provide them with constructive feedback.

Although VCSs are used mainly for software development, that's not their only use.

If we make a blog that uses a VCS for storage instead of a relational DB, and treat each post as a document, we immediately get some awesome benefits:

* **You can track your edits.** Writing an **UPDATE:** paragraph is no longer the only way to indicate that you've made a change since your original post. You might still choose to do it if your readers are in the habit of reading your blog that way, but it's not the *only* way. For example, you could point to a list of edits on a site like [GitHub](https://github.com/).
* **You can serve up posts blazingly fast.** Because most VCSs track files living in folders on your hard drive, the most convenient way to use a VCS to track your posts is to store your posts as files. It just so happens that the fastest way to serve information over the internet is from files stored in exactly that form. And what that means for you is that you can use a less powerful, less expensive server to host your blog.
* **Uploading images and videos is taken care of automatically.** When you save your files to a VCS (a step known in the software business as "committing your changes"), everything you've saved in the VCS gets uploaded automatically. All you have to do is save it into your version-contolled folder, then link to it from your post. Simple.
* **You don't need specialised publishing software.** If you're hardcore, you can create your posts with just a text editor and a VCS tool. If you're less hardcore, then I'm planning to make the software that will do this for you. It's a "someday" goal at the moment though, so no promises.

Now, this hypothetical software isn't going to work miracles. There are some things you might miss. For example, the "post from anywhere" concept becomes a bit more work for your friendly software developer, so that might not be there from the word "go". I'm envisioning a desktop app as the first editor for this guy, with your VCS of choice running in the background. I really haven't thought yet about the whole "theme" thing either. It's a work in progress, people.

*lightbulb*

Although I guess you could do something like a build process, the step in programming where code is compiled and tested, ready for deployment. I guess that's the step where you apply your layouts, assemble your RSS document, and whatever else you need to do to make your blog functional and amazing.

Mobile accessibility might also be a bit tricky - as far as I know, nobody's found a good enough reason to write a mobile VCS client yet (please let me know if I'm wrong!), and that's kind of a necessary component. Again, there'd be ways of getting around that limitation, but they're not simple, and they're not necessarily easy.

Anyway, that's the idea. Feel free to take it and run with it - or point out who has done it already.
