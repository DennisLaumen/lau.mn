--- 
layout: post
title: DAAPifying my music experience (part one)
date: 2006-09-25 22:37:06 +02:00
---
After looking at [DAAP](http://en.wikipedia.org/wiki/Digital_Audio_Access_Protocol "DAAP") (and more specifically [MT-DAAPD](http://www.mt-daapd.org/ "MT-DAAPD")) for a while I finally took the plunge today. I installed the [MT-DAAPD packages](http://sourceforge.net/project/showfiles.php?group_id=98211&package_id=105189&release_id=397897 "MT-DAAPD packages") on my Ubuntu server and started twiddling around. The config file is really easy to configure, it doesn't have to many options and has clear comments in it.

There were few options I needed to set. I needed to add the FLAC extension to the extension list and that was it really. I fired up Rhythmbox on my desktop machine and it immediately detected the DAAP share. When browsing it I got dissapointed though, it didn't read the tracks metadata and double clicking a file didn't play it.

According to the MT-DAAPD wiki it should be able to both play and read FLAC's metadata. I am calling it a night though, my DAAP experiments will continue another time.
