--- 
layout: post
title: ADP1/G1 Not Booting?
date: 2009-03-25 08:55:23 +01:00
---

[![Alternate logo.](http://upload.wikimedia.org/wikipedia/en/thumb/c/c2/Android-logo.svg/202px-Android-logo.svg.png)](http://en.wikipedia.org/wiki/Image:Android-logo.svg)

Since a month or two I am the proud owner of a Google ADP1, better known as the T-Mobile G1. This morning it was acting really weird though. When pressing the Menu-button in specific applications like the new NU.nl application and the default browser it immediately crashed the application. Conditioned as we are by sub-par software I thought a reboot might fix it. As you might have guessed after reading the subject line the handset didn't even boot after this. It started the booting process but never got to the glowing Android (it got stuck showing the non-glowing Android).

After Googlin' for a couple of minutes I couldn't find a decent solution on the internet. I decided to jack out the battery and SIM card and blow it like a NES cartridge. This didn't help though. After putting the battery back in it immediately booted the handset but it didn't get any further than before. Time for desperate measures!

The only other solution I could think of was wiping the data. Wiping the data results in a clean image so be warned: no applications, no data! Because of the connectivity with Google's services and some backup applications I regularly run, wiping the data isn't a huge deal for me.

1. Boot the handset while holding the _Home_-button.
2. It will now show a yellow triangle with an exclamation mark.
3. Slide out the keyboard and press _Alt_ and _L_ at the same time (this will show the command line interface).
4. Press _Alt_ and _W_ at the same time to perform the wipe.
5. Press and hold _Home_ and _Back_ to reboot.

The above steps fixed my handset and it booted correctly. All that's left to do is add your provider's APN settings (if you're not using T-Mobile) and enter your Google credentials and you're back up and running.
