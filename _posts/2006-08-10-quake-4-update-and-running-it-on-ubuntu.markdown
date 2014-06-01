--- 
layout: post
title: Quake 4 Update And Running It On Ubuntu
date: 2006-08-10 18:08:02 +02:00
---
Apparently I was still playing Quake 4 1.2 while there was a 1.3 update released the 25th of July. This kind of explains why so few people were online lately :).

It looks like a pretty big update. It contains:
- Gameplay tweaks like weapon balancing.
- Some performance improvements.
- A completely new gametype (Deadzone).
- A new weapon (Napalm Launcher).
- 8 new maps.
- 4 revised maps (to include Deadzone support).
- A buy mode server option (like Counterstrike has).

A complete changelog can be found [here](http://www.idsoftware.com/documents/readme_full_13.htm "Quake 4 Changelog") and the download page [here](http://www.idsoftware.com/update/quake4/ "Quake 4 Download Page").

Running it on Ubuntu works like a charm. There is a little problem with the sound however. It kind of stutters and sounds horrible. This can be fixed by starting the game with the '+set s_driver oss'  command line directive (this can also be set in a config file off course).
