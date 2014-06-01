--- 
layout: post
title: Pull that PCM slider down!
date: 2006-08-14 11:04:52 +02:00
---
As [blogged yesterday](http://blog.dfile.nl/archives/110 "Logitech Z-4 blogpost") I started playing around with my new speaker set. I was playing around with it in Windows because I was ripping a couple of CD's with the excellent [EAC](http://www.exactaudiocopy.de/ "Exact Audio Copy") (can't get it to detect drives anymore running on [Wine](http://www.winehq.com/ "Wine HQ")). As I blogged, it sounded great!

This morning however I booted my computer into Ubuntu and thought the sound on some songs sounded horrible. Most notably [Novastar](http://nl.wikipedia.org/wiki/Novastar "Novastar")'s (Dutch Wikipedia article) Caramia as it was the first song I played after booting and thus the first song in which I detected the cracking sound. So after booting back into Windows and playing Caramia I knew it wasn't a bad rip.

First thing I did after booting back into Ubuntu was play the song in [VLC](http://blog.dfile.nl/www.videolan.org/vlc/ "VLC") so I could rule out a GStreamer bug. It sounded just as horrible in VLC so it wasn't a GStreamer issue. After some googlin' around I stumbled upon the solution in the [Ubuntu forums](http://www.ubuntuforums.org "Ubuntu Forums"). Apparently I had my PCM slider maxed out in the ALSA mixer! This completely distorted the ALSA sound output (something I couldn't hear with my old el cheapo speakers).

The solution of course was very simple. Just pull the PCM slider down to 70% - 80% percent and the output sounds great!

The only thing that remains a mystery is how my PCM slider got maxed out.
