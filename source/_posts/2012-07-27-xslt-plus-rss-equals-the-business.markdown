---
layout: post
title: XSLT plus RSS equals The Business
date: 2012-07-27 21:44:31 +1000
tags: [RSS, XSLT, rendering, framework]
---
The content of the front page of this site is pretty much exactly as the content of the RSS feed, right? So why publish a separate index.html file if I don't have to? If you look closely, you'll see that it's an RSS document. But how do we make it look like the old HTML document? Well, that's the miracle of XSLT.

XSLT stands for <em>eXtensible Stylesheet Language Transformation</em>, and it's a method for presenting the data from XML files. It works by interpolating the data from the XML into a template. Since the RSS document is an XML file, we can use XSLT to render a HTML document from the RSS. I'd guess that that's the way Firefox and IE present RSS feeds - as long as the XML is structured like RSS, the browser's XSLT will present it the same way.

And you know the awesome thing? The browser does all the heavy lifting; it downloads the RSS document and the XSLT template, and transforms the two into a readable document - all you need to do on the server side is provide 2 static documents.

It's nice if you like separation of concerns as well - the XSLT is about presentation and the RSS is about information.

I get the feeling this is going to power a few more little projects.

You can read more about XSLT [here](http://w3schools.com/xsl/xsl_languages.asp).