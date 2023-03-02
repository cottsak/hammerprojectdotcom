---
layout: post
title:  "[DRAFT] Deleting Microservices and why it feels great"
date:   2023-03-02 23:17:00 +0800
---

Deleting code feels good right?

NO? 

If you said no, then go and have a think about what you've done.

For everyone else, read on..

There's a certain natural ability for an engineer to identity well organised code. It's like "good design". You don't have to be a designer to know what good design is. [You just know](https://www.youtube.com/watch?v=bLpPcBhJZBc). I suspect it's mostly by exclusion - bad design causes discomfort. We come across good design so rarely it's like finding a $100 bill on the road. You can't just ignore it. 

Well organised code is like this. It's natural to identify, even for an inexperienced engineer. Everything about it is the opposite of uncomfortable: it's easy to read, find, discover, understand, read, debug, trace, read.... did I mention read? Things feel like they have a place and that place reveals not only care and consideration on the part of the author(s) but something about the domain itself.

> Here’s what you want to get good at: deleting microservices!

It's _organised code_ which seems to have fallen by the wayside lately and I want to dive back into this ol' can of worms again: microservices vs monoliths. Actually no I don't. Why? Cos it's old and gross. Here's what you want to get good at: deleting microservices! For those working on monolithic[ish] applications where the code is organised, you deploy regularly and customers are happy, fuck off! This isn't for you. (psst! pls hire me) Everyone else: read on!

# Microliths and Monoservices

You know, we didn't hear about this term "monolith" until it's arch nemesis, the "microservice" became popular. I'm trying hard to find the spot on this line where I've been most comfortable on past projects:

```
monolith -------|------------------ microservice
```

todo: make a real fucking diagram ^

We didn't even have a continuum like this before: 

```
normal web apps -------|------------------ SOA? no! wtf!
```

[SOA](https://en.wikipedia.org/wiki/Service-oriented_architecture) or breaking the odd part of the app into a distinct service was just a component of ones architecture. It wasn't the defining trait such that you could use it like this and call the whole application design an "SOA app". We do that with microservices. You're either "doing microservices" or you're not. And since one needs to be labelled as "doing it" or "not doing it" (by some odd social construct I don't fully understand), we need to have a label for the "not doing it" group - the loosers or kids who are "uncool"; the "boomers"!? 🤷‍♂️🤦‍♂️ 

So in comes "monoliths". It's there so we can explain the other end of the spectrum, right? If you're not doing microservices you've gotta be doing a monolith. 

So in my quest to name the thing that you have when you start with two tightly coupled microservices:

todo: diagram showing two simple ms, each with an API, app and db

and then collapse them into one:

todo: diagram showing a single ms, but the api/app/db now includes everything from both

I tried to venture into naming and found Microliths and Monoservices. But of course [naming is hard](https://martinfowler.com/bliki/TwoHardThings.html) and the usages I found for these terms were equally old and gross. So I don't have a term! dammit!

# Why go and delete a microservice?

todo: problem space


# Ideally, you might want to consider going back to a monolithic app

Not because I like the term "monolith", but because it's the simplest wat to describe where an architecture should begin most of the time. It's [considered fairly safe to start with a monolithic app](https://www.martinfowler.com/bliki/MonolithFirst.html) and go from there. Soon chaos kicks in and you need to organise your code. But if you hire experienced engineers, they can show you and your team how to do this. It's not rocket surgery - half of the web is built on monolithic web applications like ages ago and many of them scale just fine. 

So maybe your architecture evolves to extract distinct services that you can actually develop and deploy independently. You can even scale them separately too - cos everyone has scaling problems when they start out right? 😉

But the advice usually goes like this:

* Start coupled because its easier to ship and learn.
* Refactoring coupled code is easier than when the coupling is across service boundaries and takes hard dependencies on refactoring coordination, network/http, service discovery and different cloud resources than a single monolithic app.
* You also don't want to extract something to it's own service until you understand it well. That means it needs to be shipped and used "in anger" by customers for some time and probably experience a number of iterations before your team is qualified to say they "understand it", and specifically:
* Understand it's boundaries! You can't hope to separate something unless you are highly confident about where the former should end and the new should begin. Doing this up front with no time in production and no deep understanding by the team is a fast road to failure.

Once you have one or two very distinct and independently useful services working well, you're "doing microservices" or some form of SOA. Cool points to you! Coming back from this is easier because you do it slowly and this also ensures that the odds of a misfire are lower because the decision is based on a lot of experience. 

But once you've started down the microservice journey, and especially if it's from the start or just too early or too completely - you might find you're in pain. "Going back" [to a monolith] seems like a step backwards because it is. It's one of those _one step back and two steps forward_ kinda things. Or _live to fight another day_ or whatever! Insert your own wise catchphrase. 

There may be some fear or ego that can get in the way of taking a holistic strategic path to striking "microservices" from the company engineering blog. It's not going to be popular at the pub with your developer friends: "yeh well guess what we decided to do this week? Stop using microservices completely and go back to a monolith". No more beer for you!

# How to delete a microservice

todo: explain the collapse method and how to choose a candidate

This is a piecemeal approach, far less courageous than strategically choosing to kill all of them. But one that may be more palatable to your risk averse engineering leaders. I mean after all, they've just been all cool and shit with their microservices architecture and it's eating them alive! You gotta empathise with their aversion to risk okay.