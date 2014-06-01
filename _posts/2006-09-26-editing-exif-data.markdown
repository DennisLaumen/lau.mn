--- 
layout: post
title: Editing Exif data
date: 2006-09-26 23:37:57 +02:00
---

My father recently purchased a new digital camera. It's a pretty nice device but not the subject of this blog post. The subject of this blog post is the excellent package [jhead](http://www.sentex.net/~mwandel/jhead/ "jhead") (When using Ubuntu ``sudo apt-get install jhead`` does the trick). On it's official site the application is described as:

> "Exif Jpeg header and thumbnail manipulator program"

Why did I need an Exif editor? When my father showed me the camera I immediately started taking pictures all over the place. The system date of the camera was not yet set which meant that all the pictures I took today were timestamped December 31st 2005.

Using jhead i fixed it with the following command:

``jhead -ts2006:09:26-12:00:00 *.JPG``

Which sets the Exif date of all the \*.JPG files in the current folder to September 26th 2006 12 o'clock.

PS Wordpress should really add the word 'blog' to their spell checker!
