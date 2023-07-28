---
layout: post
title:  "complexity very, very bad"
date:   2023-07-28 12:00:00 +0800
---

I don't remember how but I stumbled onto [grugbrain.dev](https://grugbrain.dev) last week.

It's gold. 

I could literally end this post on the line above. But I did wonder about how junior devs might find this content. I personally find it to be amazingly written. It's just my kind of comedy with a dash of WAKE THE FUK UP NEO! 😆 But I'm not exactly sure whether a green engineer will understand much of it and gain the most value possible. So I wanted to add some of my thoughts. The following is just a commentary. I don't want to subtract anything at all, but if I'm lucky, maybe unpack things for a less-seasoned audience. 

Let's start with this section --

## The Eternal Enemy: Complexity

> apex predator of grug is complexity

Complexity is quite literally the biggest threat to any software engineer and all of software engineering. Why? Well I'll try to uncover that below and close with a few of my own thoughts at the end.

> complexity bad  

Don't misunderstand this point. It's worth repeating. 

I actually struggled to agree with this a little and it was largely "semantics". But semantics are important because they convey meaning. Don't let someone criticise you because you're "getting hung up on semantics" - people who get hung up on semantics usually care about clarity. This might mean that they want to understand things deeply. Don't miss an opportunity to work with someone like this. 

There is this narrative in the software engineering community that roughly tries to draw a distinction between **complexity** and that which is **complicated**. That alone deserves a post all on it's own, but the short version for me is that I'm now ok with allowing them to exist in the same container. There might be an occasional reason why complexity is necessary. This is usually the hang up - how can you avoid something that you need? Now I wonder if this is just another problem solving activity. 

If you think you truly need complexity `n`, then try to design it out. Try to reduce `n` or delete it altogether. Remember, "[the best part is no part](https://hammerproject.com/2022/11/17/smashing-entropy.html)".

> say again:  
> complexity very bad  
> you say now:  
> complexity very, very bad

Say it out loud even. If the guy across the desk from you gives you one of those "what a weirdo" looks, then link them to this post. Just be like "he told me too" while pointing at your screen. 

> given choice between complexity or one on one against t-rex, grug take t-rex: at least grug see t-rex

The subtlety here is that complexity can often be hard to recognise. This is especially terrifying when you realise that complexity is kinda glorified in our industry, particularly among younger engineers who are out to prove themselves. It's like lifting at the gym: if you can lift something heavy, you're cool right? Well, if you can build something hard, or solve a hard problem, or a complex problem, then you're cool right? Just get your flex on and show the world how great you are...?? 🤷‍♂️ I'm not saying that some engineers try to hide complexity on purpose. But there is a large cultural incentive to add it and because it hides in dark corners and is hard to see, its a very real problem. 

Training alone won't be enough to help you spot complexity. It comes mostly with time. But one signal is pain. If something feels harder than it should, then maybe it's too complex. Of course this is pretty subjective and a "gut feel" kind of thing. But soon you will learn to notice the sensation. Listen to it. [Search your peelings](https://youtu.be/hVrIyEu6h_E?t=266).

> complexity is spirit demon that enter codebase through well-meaning but ultimately very clubbable non grug-brain developers and project managers who not fear complexity spirit demon or even know about sometime

I could be wrong, but I suspect that "non grug-brain developers" are actually "big brained developers" [as referenced elsewhere in the article](https://grugbrain.dev/). "non grug-brain developers" may also refer to junior or less-seasoned engineers. Or maybe devs that don't share some of Grug's qualities, like humility. Ego is certainly a common trait in the software engineering industry. "It's ok to be wrong" is an important life lesson. But applying this early in your SWE career will give you a significant advantage. 

As I mentioned earlier, complexity is popular in our industry at times. This may be part of the reason why its not respected or even feared. Fear is important - it keeps you from falling off the edge of the cliff. It's a signal about danger. Complexity `==` danger. If an engineer has a hard time properly respecting complexity then a non-technical person like a project manager may find it harder still. 

Keep in mind that as a new engineer, you won't know how to spot complexity at times. You often need a wide variety of experiences to see how complexity manifests in different contexts to attribute patterns to its appearance. There are few simple ways around this. You will learn over time. Some developers can't see it [yet]. There's no shame in this. 

> one day code base understandable and grug can get work done, everything good!  
> next day impossible: complexity demon spirit has entered code and very dangerous situation!

This is obviously an exaggeration, but complexity can lie in wait so well that it can appear to jump out of nowhere. It's the [forrest for the trees](https://en.wiktionary.org/wiki/see_the_forest_for_the_trees) thing. Or simply that moment when you take a step back because you've been [in the weeds](https://digitalcultures.net/slang/in-the-weeds/) on a particular thing for so long that you don't see what's happened at a macro scale. 

The other thing to call out here is that once complexity has taken hold, it can literally grind productivity to a halt; or at least make changes extremely slow. Often this comes about purely from the next developers inability to understand whats going on easily. Most engineers don't write code. That's not what we do for work. A programmers primary time sink is reading code, not writing it. So it's critical that you as a developer can help another developer read and understand what's going on. That's not just scoped to your function or file, but the application and system as a whole. Complexity will destroy this ability to read and understand. And since engineers are typically clever people, they will work around complexity at times not even realising that said workarounds are increasing the level of complexity! This doesn't seem wrong at the time because that developer has a good understanding in their head. But the next guy? Good fuken luck!

EDIT: One thing I didn't really consider properly is how "exponential" this can grow. I guess this makes sense as to why it can _feel_ like it happens overnight. I want to give this more thought. Grug recommends: [Complexity Budget](https://htmx.org/essays/complexity-budget/)

> grug no able see complexity demon, but grug sense presence in code base

Even experienced engineers can't often put their finger on the exact source or target of the complexity. Sometimes it's a sense or a gut feeling. I've seen developers cringe, or curl up their face. It's an instinct that you develop over time and various projects. 

> demon complexity spirit mocking him make change here break unrelated thing there what!?! mock mock mock ha ha so funny grug love programming and not becoming shiney rock speculator like grug senior advise

This is an analogy to the "complexity spirit demon" having an intelligence of its own. It's genuinely hard to counter this thought if I'm honest. I joke a lot, but here I am very serious: given that the complexity is almost always sourced from another person, I don't think its a stretch to describe the "demon" as an intelligent entity. Think I'm crazy? Well, if you wanna go deep on this then consider that [the universe might actually have a tendency to entropy or disorder. And we humans facilitate this](https://youtu.be/DxL2HoqLbyA). So every line of code that's added is in fact just a little more potential for complexity and peer-induced pain. This is part of the reason why experienced developers love deleting code so much. Sometimes you just don't know where the disease is and you wanna rip large chunks out in the desperate hope that your artillery strikes will land on the enemy. 

And other times, you just wanna start again from scratch. 

Have you ever seen a senior engineer crying in the corner?  
My money is on complexity.  
I don't think Grug has chosen the word 'demon' lightly. 

I'm not entirely clear on what "shiney rock speculator like grug senior advise" means but I suspect its something to do with the fact that getting paid well, often doesn't counter the pain that one can endure at the hands of complexity. I actually love software engineering as a creative pursuit all on its own. Sure I also need to feed my family but there are some things in this world that will threaten even the intrinsic love you hold for something: complexity is that to software engineering for many of my seasoned friends and colleagues. 

> club not work on demon spirit complexity and bad idea actually hit developer who let spirit in with club: sometimes grug himself!

Sometimes you can't simply attack the complexity directly. I've seen this time and time again. We engineers love to make cool stuff. Sadly tho, most of the "cool" things we build are not necessary, or are unnecessarily complex. This is where attacking the complexity becomes attacking another person. This then becomes a human relationship problem. And if you you thought being a programmer meant you could escape human relationship problems: you'd be wrong!

> sadly, often grug himself

It wouldn't be the first time I built something in an app and then later ripped it out myself due to complexity. It hurts and is humbling. So do it often! That's how you grow.

> so grug say again and say often: complexity very, very bad

The point can't be drilled hard enough. This is why I wanted to annotate the article with my thoughts. I'm sure I'll be commenting on this theme for the rest of my career, probably at the pain of my grandchildren when I'm old and can't remember what I said 10 seconds ago. Hi guys! ❤️

If you're new to software engineering, and you can't see how all this fits in to your life, work or just the space in general then remember this:

_Complexity is real and it's hunting you right now. But as an inexperienced engineer, you're vulnerable to its guile and tricks. It's going to tempt you with shiny packages and tools. It's going to bend your mind and titillate your taste buds at conferences and with awesome presentations. Soon you will think you know more than someone else and next thing you know, you're writing some "cool" code that will impress all of your peers. It has you now. You're its bitch!_

The best counter to complexity as a new engineer is humility and open mindedness. I wish I applied more when I was younger and the more experienced I get, the more I try to focus on these things. Learn from clever peers. Learn from experienced engineers. 

May The Force be with you. 🙏

--

Thank you to JakeGPT, Ruegen and Grug himself for edits, comments and feedback.  

Please discuss on [Dev.to](https://dev.to/mattkocaj/what-junior-devs-need-to-know-about-complexity-233n) or [LinkedIn](https://www.linkedin.com/posts/activity-7090548647792148480-9ZA1)