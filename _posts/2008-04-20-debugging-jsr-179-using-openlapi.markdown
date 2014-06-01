--- 
layout: post
title: Debugging JSR-179 using OpenLAPI
date: 2008-04-20 18:46:15 +02:00
---

[Global Positioning System](http://upload.wikimedia.org/wikipedia/en/2/2f/NAVSTAR_GPS_logo_shield-official.jpg)

Developing a [J2ME](http://en.wikipedia.org/wiki/Java_Platform%2C_Micro_Edition "Java Platform, Micro Edition") application using the **Location API** can be pretty annoying. It's quite difficult **debugging **an application which uses a [GPS](http://en.wikipedia.org/wiki/Global_Positioning_System "Global Positioning System") device as a form of input. You usually **can't get a GPS fix in a building** (which is where most people do their developing) and even then you would have to continually get up and walk around to see if your new bit of code functions properly.**[OpenLAPI](http://openlapi.com "Location API for Java ME")** to the rescue! OpenLAPI is an **open source implementation** of **JSR-179** (J2ME's Location API). It contains the complete JSR-179 API and then some... One of the extra features solves the aforementioned debugging problem. We'll come back to those features later on in this post.In a previous blog post you read how to create an instance of the **LocationProvider**. The LocationProvider is basically an abstract factory and instances are built on a set of **criteria**. As a developer you don't have any direct control over what type of LocationProvider you receive. You just tell the API which demands you have and the API gives you the implementation closest to your demands.

{% highlight java %}
LocationProvider provider = LocationProvider.getInstance(new Criteria());
{% endhighlight %}

OpenLAPI however gives developers some extra flexibility when creating a LocationProvider. You can choose to use either a GPS device, an [NMEA](http://en.wikipedia.org/wiki/NMEA_0183 "NMEA 0183") log file, a [KML](http://en.wikipedia.org/wiki/Keyhole_Markup_Language "Keyhole Markup Language") file, a LandmarkStore or your own specific implementation of the LocationProvider class. All you have to do is **add a configuration file** called ``OpenLAPI-mode.txt`` to the root of your [MIDlet](http://en.wikipedia.org/wiki/MIDlet "MIDlet"). In this file you place ``GPS``, ``NMEA``, ``KML``, ``LMS`` (for the LandmarkStore) or the full class name (including packages) of your own LocationProvider implementation. Now all we need to do is add **one of the log files** in the same directory as the configuration file and we are done (more details can be found [here](http://thinktankmaths.com/technologies/openlapi/docs/ "OpenLAPI documentation")).Using the feature mentioned in the paragraph above we can now debug our application with ease. We can use NMEA logs from GPS devices or create a route in [Google Earth](http://earth.google.com/ "Google Earth") and export it to KML. Doing this really makes GPS development **a lot quicker and more reliable**.
