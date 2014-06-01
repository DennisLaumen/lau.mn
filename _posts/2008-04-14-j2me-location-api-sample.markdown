--- 
layout: post
title: J2ME Location API sample
date: 2008-04-14 19:45:18 +02:00
---

Recently I have been playing around with [J2ME](http://en.wikipedia.org/wiki/Java_Platform%2C_Micro_Edition "Java Platform, Micro Edition"). One of the cool features of J2ME is the [Location API (JSR-179)](http://jcp.org/en/jsr/detail?id=179 "Location API for J2METM").

Firstly, remember to import the Location package.

{% highlight java %}
import javax.microedition.location.*;
{% endhighlight %}

Let's get to the meat of the matter.

{% highlight java %}
// Criteria can be used to filter which GPS device to use.
Criteria criteria = new Criteria();
criteria.setCostAllowed(true);
criteria.setPreferredPowerConsumption(Criteria.NO_REQUIREMENT);
// Get a location provider based on the aforementioned criteria.
LocationProvider provider = LocationProvider.getInstance(criteria);
// Try to fetch the current location (using a 3 minute timeout).
Location location = provider.getLocation(180);
// Get the coordinates of the current location.
Coordinates coordinates = location.getQualifiedCoordinates();
if (coordinates  != null) {
	// Get the latitude and longitude of the coordinates.
	double latitude = coordinates.getLatitude();
	double longitude = coordinates.getLongitude();
} else {
	// You didn't get any coordinates.
}
{% endhighlight %}

As you can see it's pretty easy fetching your position's latitude and longitude. It's not a piece of navigation software yet, but it's a pretty cool first step.
