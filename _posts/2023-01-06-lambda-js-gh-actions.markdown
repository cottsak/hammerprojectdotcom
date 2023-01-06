---
layout: post
title:  "Key learnings after 10h diving into Lambda, js and Github Actions"
date:   2023-01-06 08:48:00 +0800
---

I recently heard that you can [learn almost anything if you spend 20h of unbroken, concentrated effort](https://youtu.be/JPCJEtMXOu0?t=1347). Of course you won't become an expert and everyone has to pee, so the statement comes with some obvious caveats. But I thought I would try something new and dump most of a weekend onto a small project. 

## The Story

I've been suffering from a very not-painful first-world problem lately. 😋 When I get out of my car and go into the house I usually have my hands full and I want to lock the car behind me. To overcome this, I would like to ask Siri to [lock the car](https://youtu.be/awui-L4J_p8) instead of opening the app and tapping it. I've discovered that the Tesla app needs to be open for the car to take commands via Siri. This won't help when the phone is in my pocket locked and all I have to access "hands free" is the Apple Watch. So I asked myself 

> Can I create a web endpoint that I can call with [Shortcuts](https://support.apple.com/en-gb/guide/shortcuts/welcome/ios) which can be invoked using Siri?

Turns out I can. So I set out to create an endpoint that is long enough to be "secure" so that I could write a simple Shortcut that I could use with Siri from my Apple Watch while my hands were full. Something like this:

```
aws.thingy.com/lambda/lock-car?secure-token=reallylongassrandomstringthatyoucantguesssothisiskindasecure
```

After knocking out a README with a set of goals and a list of TODOs to check off as I made progress, I spent about 10 hours over a weekend trying to get something to work. I used [`serverless`](https://www.npmjs.com/package/serverless) for making [Lambda](https://aws.amazon.com/lambda/) easier, [Github Actions](https://github.com/features/actions) for the deploy pipeline and store my credentials; and sadly I rolled my own `access_token` refresh logic because I couldn't find a helper that just did that for me! wtf!? 

![using a README as a backlog. do it!](/assets/some%20of%20the%20lock-car%20readme.png)

I now have a Shortcut that works using Siri; a Lambda that can refresh it's own token and a reliable way to lock my Tesla without my hands. It even speaks the text response from the HTTP call: "car is locked" which is kinda satisfying.

![the final product](/assets/lock%20car%20shortcut.jpg)

## Key Takeaways for Me

* **[`serverless`](https://www.serverless.com/) is amazing!** Sure it's the first thing I found. But it made it super easy to set up my js project locally, run it locally and deploy it from the command line. I can't understate the importance of a fast feedback cycle. Since I lack a lot of debugging experience with vscode/ts/js it is important that I can `console.log` easily and run locally to try/fail/repeat. 

![the Quick Start in the README is super terse with serverless](/assets/some%20of%20the%20quick%20start%20from%20the%20readme.png)

* **Lambdas are pretty quick.** Cold starts from the Shortcuts app can be about 5s end-to-end and this includes a token refresh. When the lambda is warm and using the new `access_token`, it can be as quick as ~1100ms according to CloudWatch.

![logs showing the token refresh on a cold call](/assets/cold%20start%20and%20token%20refresh.png)

* The js was pretty straightforward and I'm no js/ts expert. I was cautious and used callbacks instead of Promises. So I should try that next time. 😋
* **Actions start and run _really_ fast!** Having come from the "old days" where pipelines were <10m to large microservices codebases where pipelines are back to running ~30m, it is super refreshing to have a pipeline which is not only short in terms of duration (1-2m total) but kicks off within a couple of seconds of my pushing my code to `master`. 🥰
* I didn't feel the need to use [Parameter Store](https://docs.aws.amazon.com/systems-manager/latest/userguide/systems-manager-parameter-store.html) as the credentials in Secrets are one way and `serverless` hides them in the logs when mapping params (or is it [actually Github doing this?](https://docs.github.com/en/actions/security-guides/encrypted-secrets#accessing-your-secrets)). I accept that for a "professional" application, I wouldn't do it this way, but it's fine given the context. Feel free to tell me why I'm wrong. 😋
* I wanted to create a "revocation" call to pair with this automation but I changed my mind on that. Mostly because the commonly accepted approach with an integration platform with API credentials is to reset the password on the primary account and this invalidates all derived keys. I tested this and it works so I think that's fine for now. Yes, I have a production key stored in Github and as an ENV var in AWS which is as good as my Tesla password, but the attack surface is pretty limited I think. There are other apps which ask you to authenticate, and then they persist refresh tokens. I don't think my solution is worse or creates more risk than those.

## Whats Next?

Here are just some random thoughts about things I might want to change or improve:

* setting up a new Shortcut to start charging the car
* how will it be structured in Lambda?
* how can I share code like the token refresh logic between two functions?

I hope you found this interesting. I'm constantly amazed at what can be accomplished if you set your mind to a clear goal.

Discuss on [dev.to](https://dev.to/mattkocaj/key-learnings-after-10h-diving-into-lambda-js-and-github-actions-4g3i)

<!-- 
todo: read 30m of `The Elements of Style` and do a 15m timebox edit of the post. 
-->
