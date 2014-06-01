--- 
layout: post
title: GtkOrphan
date: 2006-08-29 19:12:23 +02:00
---
[DebOrphan](http://freshmeat.net/projects/deborphan/ "DebOrphan") is a package I have been using for a while now. It's a command-line tool for debian-based distros and it helps you remove orphaned packages. While browsing a bit through Synaptic I stumbled upon [GtkOrphan](http://www.marzocca.net/linux/gtkorphan.html "GtkOrphan").

As it's name implies it's a GUI front-end for DebOrphan. It lists all orphaned packages on your system and you can remove them with a couple of mouse clicks. Really great for cleaning up all those packages wandering around on your system. It has a few clumsy GUI issues but nothing too disturbing (as it's not a package you will use every day).

DebOrphan (and thus GtkOrphan) has a big downside though. It lists all top-level packages, i.e. packages on which no other package depends,  which means you shouldn't go around deleting all the packages it suggests. You need to have a thorough understanding of all the packages on your system which makes it less usable for newcomers.

Have fun using it, but don't come back crying when you devastated your system.
