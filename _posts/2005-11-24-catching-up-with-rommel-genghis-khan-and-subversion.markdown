--- 
layout: post
title: Catching up with Rommel, Genghis Khan and Subversion
date: 2005-11-24 20:24:58 +01:00
---
Long time no blog...

I have been pretty busy lately which is why I didn't blog for a while (hmm... I keep repeating myself on this one :D). I have been real busy with school the last couple of weeks and had some personal projects I really needed to finish.

After I did finish these I took a couple of days of from life and did absolutely nothing except for [hunting the Afrika Korps out of Africa](http://www.callofduty.com/cod2/) (Noisy Flash-site warning!!!) and [working on my campaign for Mongolian World Domination](http://2kgames.com/civ4/home.htm)(Noisy Flash-site warning!!!).

The last week I decided to finally build a [Subversion](http://subversion.tigris.org/) server here. After [Loe](http://lgespee.blogspot.com)'s filesystem hassles and version fuckups I decided to do him a favour ;).

Initial setup didn't go so great, I had trouble configuring the thing correctly and didn't really understand the authorization part of the configuration. I was trying to run it with the svnserve daemon and a SSH tunnel but I couldn't get it to work flawlessly.

After screwing around with it and finally RTFM I decided to go the [Apache](http://www.apache.org) &amp; [DAV](http://www.webdav.org/) route. This went pretty easy I must say. After configuring it I have been playing around with it and started using it for some school projects and I must say I really like it.

After the initial installation I apt-getted [WebSVN](http://websvn.tigris.org/) as well. It is a [PHP](http://www.php.net) web interface for Subversion and it's pretty nice. It has got template support and supports [RSS](http://www.scripting.com/) feeds for the repositories out of the box (hooray for RSS!!!).

I am going to wrap it up for this post. I am considering writing a Subversion tutorial one of these days but I will probably never get around to it :D.
