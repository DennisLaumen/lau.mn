---
layout: post
title: "Given-When-Then with Spock"
date: 2013-04-06 20:01
---

As a recent newcomer to the [Groovy][groovy] and [Grails][grails] world I only recently discovered [Spock][spock]. Spock is a testing and specifications framework for Groovy applications (but Java apps are welcome too!).

One of the nice features of Spock is the support for so-called _blocks_. These blocks start with simple labels like _when_ and _then_. These labels can even be decorated with a nice description which explains in natural language what the blocks are intended for.

Most of the examples of Spock specifications look like this:

``` groovy
def 'pushing an element on the stack'() { // A nice description of the feature!
    when: // This is an example of a block, it starts here and ends at the next block or the end of the method.
    stack.push(elem)

    then: // These blocks don't even have labels, I'll show them in a minute!
    !stack.empty
    stack.size() == 1
    stack.peek() == elem
}

```
 
Although this is fine in and of itself I prefer to structure my tests according to a user story's acceptance criteria. When doing this I use the now ubiquitous [given-when-then scenarios as defined by Dan North and Chris Stevenson][bdd].

For example, consider the following user story (the following examples are from [Dan North's excellent article I just linked to][bdd]):

> +Title: Customer withdraws cash+  
> _As a_ customer,  
> _I want_ to withdraw cash from an ATM,  
> _so that_ I don’t have to wait in line at the bank.

One of the possible given-when-then scenarios looks like this:

> +Scenario 1: Account is in credit+  
> _Given_ the account is in credit  
> _And_ the card is valid  
> _And_ the dispenser contains cash  
> _When_ the customer requests cash  
> _Then_ ensure the account is debited  
> _And_ ensure cash is dispensed  
> _And_ ensure the card is returned

Unfortunately, I couldn't find anything hinting at support for these scenarios using Spock (like _given_ and _and_ blocks). As per usual, I wasn't looking very well as Spock gives you all the needed information in [its documentation][spock-basics]. I wrote this blog post anyway just to help the folks googling for _"spock given-when-then"_ and _"spock acceptance criteria"_ (and to remind myself of my own oversight of course!).

Using Spock's aforementioned support for blocks and labels one could implement the scenario above as follows:

``` groovy
def 'Account is in credit'() {
    given: 'the account is in credit' // Look a label! Like I promised earlier!
    def account = new Account()
    account.credit = 2000
    
    and: 'the card is valid'
    def card = new Card()
    card.valid = true
    card.account = account
    
    and: 'the dispenser contains cash'
    def dispenser = new Dispenser()
    dispenser.cash = 25000
    
    when: 'the customer requests cash'
    dispenser.requestCash(100, card)
    
    then: 'ensure the account is debited'
    account.credit == 1900 // No explicit assertion API, lovely! 
    
    and: 'ensure cash is dispensed'
    dispenser.cash == 24900
    
    and: 'ensure the card is returned'
    !dispenser.hasCard
}
```

I think it looks and reads great! What I especially like about Spock is that it's really flexible and powerful but has a minimalist syntax.

So, are you still looking for nice specification framework for Groovy (or Java)? Stop looking, go download [Spock][spock]! 

  [groovy]: http://groovy.codehaus.org/ "Groovy - Home"
  [grails]: http://grails.org/ "Grails - The search is over."
  [spock]: https://code.google.com/p/spock/ "spock - the enterprise ready specification framework"
  [bdd]: http://dannorth.net/introducing-bdd/ "Introducing BDD"
  [spock-basics]: https://code.google.com/p/spock/wiki/SpockBasics "SpockBasics"
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
