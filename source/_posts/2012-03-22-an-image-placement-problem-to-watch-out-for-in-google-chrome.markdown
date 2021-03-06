--- 
layout: post
date: 2012-03-22 11:25:31 +1000
title: An image placement problem to watch out for in Google Chrome
tags: 
  - css sprites
  - google chrome
  - web dev
---
Google Chrome has an interesting little thing that it does, where it decides how the page will be laid out <em>before</em> it knows the dimensions of all the elements. For example, if you create a <code>&lt;div&gt;</code> tag with a large image in it, Chrome will calculate the height of the div before the image has loaded. That's right - it figures out the height of the image's container <em>without necessarily knowing the size of the image</em>.
  
So who cares? What does this mean?
  
Well, if you have elements styled as <code>position: absolute</code> in your page, you might find that they start out correctly placed, but they don't move with the rest of the page when the image loads. This means that you have badly placed images sitting around in your page, making the whole thing a horrible mess.
  
Alternatively, you might have a set of images that are meant to sit in a nice little row inside a <code>&lt;div&gt;</code>, but they end up wrapping onto an extra line because Chrome didn't wait until they'd loaded before it figured out how wide to make the <code>&lt;div&gt;</code>.
  
And what can you do about it? Here are a couple of options:
  
* **Specify the dimensions of your images in code.** Don't leave it to the image to tell the browser what size it is, because by the time the browser finds out, it may well be too late.<br />
  You can do this in a couple of ways: 
  * Use the <code>width</code> and <code>height</code> attributes of the <code>&lt;img&gt;</code> tag. This is not very good in terms of separation of concerns, but it will get the job done.
  * Use CSS to specify the width and height of your image, or alternatively the size of its container. This is better separation of concerns, and CSS <em>should</em> load early enough in the rendering process that you don't get the same problem you've been having with your images.
* **Use <a href="http://css-tricks.com/css-sprites/">CSS image sprites</a> instead of individual image files.** This is basically the same as using CSS to specify your image dimensions, or rather it <em>includes</em> same. Image sprites force you to specify the size of the image, otherwise it won't display correctly. This means that you will notice while you're working on the page if something is not quite right, and be able to fix it there and then. You won't have to waste time later on, coming back to somewhere you've already been.
  
Hopefully this helps you figure out a problem some time. If not, just remember it was here.
