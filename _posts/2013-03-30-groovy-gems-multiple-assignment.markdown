---
layout: post
title: "Groovy Gems: Multiple Assignment"
date: 2013-03-30 19:07
comments: true
categories:
- Groovy
- Programming
- Groovy Gems
- Java
- Multiple assignment
---

I've recently started a new job at [IHomer][ihomer]. Besides the differences in organization with my former employer they also use a couple of technologies I wasn't exposed to before. One of these technologies is the [Groovy][groovy] programming language, a dynamic language which runs on the JVM. As a Java refugee there's a lot of new stuff here (although I've seen most of it in other languages in my spare time).

Yesterday, Groovy's support for [multiple assignment][multiple-assignment] made me happy. I was receiving some comma-separated data from another system which  needed to be parsed. In Java this would've required a couple of verbose lines of code.

{% highlight java %}
public class MultipleAssignment {
    
    private String a;
    
    private String b;
    
    private String c;
    
    public MultipleAssignment(String input) {
        String[] splitInput = input.split(",");
        a = splitInput[0];
        b = splitInput[1];
        c = splitInput[2];
    }
}
{% endhighlight %}

The Groovy version of the above code is a lot more succinct!

``` groovy
class MultipleAssignment {
    
    def a
    
    def b
    
    def c
    
    MultipleAssignment(input) {
        (a, b, c) = input.split(',')
    }
}

def ma = new MultipleAssignment('1,2,3')

assert ma.a == '1'
assert ma.b == '2'
assert ma.c == '3'
```

It's not a massive language feature and I know a lot of languages which support similar constructs. It's always been the small things that make me happy though, and that single line of code made me really happy yesterday.

  [ihomer]: http://www.ihomer.nl "IHomer – thuis in IT"
  [groovy]: http://groovy.codehaus.org/ "Groovy – Home"
  [multiple-assignment]: http://groovy.codehaus.org/Multiple+Assignment "Groovy – Multiple Assignment"
