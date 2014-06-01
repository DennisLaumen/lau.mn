--- 
layout: post
title: Advanced breakpoints in Eclipse
date: 2008-05-22 19:11:50 +02:00
---

## Breakpoint properties?

For the last couple of months I have been using [Eclipse](http://www.eclipse.org "Eclipse (software)") more and more in both a personal and a professional setting. Eclipse can be an **overwhelming and daunting** [IDE](http://en.wikipedia.org/wiki/Integrated_development_environment "Integrated development environment") but is a very powerful one too. One of the features I hadn't discovered until recently is the **breakpoints properties screen**. This screen has a number of cool features but I'd like to highlight two of them in this blog post.

## Hit count

Eclipse allows you too only suspend the thread for [debugging](http://en.wikipedia.org/wiki/Debugging "Debugging") when hitting the [breakpoint](http://en.wikipedia.org/wiki/Breakpoint "Breakpoint") a certain number of times. Look at the example code below.

{% highlight java %}
for (int i = 0; i <= args.length; i++) { 
	System.out.println(args[i]);
}
{% endhighlight %}

Imagine a much more complex version of the scenario seen above. You're skipping through arrays and suddenly an ``ArrayIndexOutOfBoundsException`` is fired. Wouldn't it be easy to be able to debug this piece of code without having to click through the loop a **gazillion times** until you reach the phase of the loop you're interested in?Eclipse makes this all possible in its breakpoints properties screen. This screen is shown below and can be opened by **right clicking a breakpoint** and selecting properties in the menu. As you can see in the image below you **enter a numerical value** which indicated **how many hits** a breakpoint should get before suspending the thread and allowing you to dive into the code.

![hit count](/2008/05/22/advancedbreakpointshitcount.png)]

## Conditional breakpoints

An even more powerful feature than the one shown above is the **conditional breakpoint**. An example of this can be seen in the picture below.

![condition](/2008/05/22/advancedbreakpointscondition.png)

Using the settings seen in the image the breakpoint only suspends the thread when the condition in the text box is true. You can enter any [boolean](http://en.wikipedia.org/wiki/Boolean_datatype "Boolean datatype") condition in this box.Both of the above features allow for some **very, very powerful debugging**.
