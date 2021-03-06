---
layout: post
title: How to configure your Fritz!Box VoIP connection with iiNet
tags: [phone, VoIP, router, Fritz!Box]
date: 2013-08-09 22:24:12 +1000
---
I just got my new phone connection working with my new router. I thought I'd write it down here in case I need to do it again some time.

The good news is that you can do all the basics with the wizard. The even better news is that I don't have any advanced requirements (yet). :)

So log in to [your router](http://fritz.box) and select "Wizards" from the menu on the left. Then click "Manage your own phone numbers". This will start the wizard for you.

On the screen that comes up, click "Add Telephone Number".

Then for a VoIP connection (e.g. on iiNet's Naked DSL plans), select the radio button that says "Set up Internet telephone number", and click "Next".

**Here's the bit where things don't quite line up.** You'll be presented with a screen where you're asked for:

* an Internet number
* a User name
* a Password
* a Registrar

And what you get in your email from iiNet is:

* a phone number
* a password
* a Voicemail PIN
* a SIP domain 
* a SIP server

Don't panic! You have all the information you need. You just have to know where to put what.

<table>
  <tr> 
    <th>Fritz!Box</th>
    <th>iiNet</th>
  </tr>
  <tr>
    <td>Internet number</td>
    <td>Phone number</td>
  </tr>
  <tr>
    <td>User name</td>
    <td>Phone number (yes, that's right)</td>
  </tr>
  <tr>
    <td>Password</td>
    <td>Password</td>
  </tr>
  <tr>
    <td>Registrar</td>
    <td>SIP domain</td>
  </tr>
</table>

Once you fill out the form and click Next, the router will test the connection details you entered. If all is well, you should be able to make calls now. :+1:

If not, you may need to fill in a couple more things. 

1. Hop into Advanced mode for a minute. Do this by clicking on the "Expert mode" link at the top of the page. This will warn you about leaving the wizard. It's OK, you'll be fine.
2. Get back into the wizard by clicking on the "Wizards" link at the left, then choosing the "Manage Your Own Phone Numbers" wizard.
3. You should now be looking at the table of phone numbers, which now includes your number. Click the pencil to edit it.
4. Here's where you'll see the extra stuff. The main one we're interested in is the "Proxy server" field. Grab the **SIP server** link from your email, and pop it in there.
5. Just for good measure, check the box immediately below that, which says "Use Internet telephone number for registration".
6. Click OK to save, and we're done! You should now have a working VoIP phone.