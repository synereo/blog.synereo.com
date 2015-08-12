---
layout: post
status: publish
published: true
title: Top 5 Things You Can Do With Synereo NOW
date: '2015-08-12 08:00:00 +0200'
author: Nicola Minichiello
---
The most common questions we get asked are "When are you shipping?"  and “when can I start playing with the bits?”.

The short answer is - we’ve shipped, and you can deploy nodes and work on developing decentralized apps using Synereo’s P2P stack RIGHT NOW. 

![image alt text](/img/uploads/aws.png)

### How do you get started?

We already have a poor man’s one click install as an [AMI](http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/AMIs.html). If you want to play with one, [send us ](mailto:hello@synereo.com)your Amazon account # and we’ll give you access to the AMI so you can get started. 

This process will become even easier as we plan on releasing a Docker-based one-click deployment package in just a few short weeks. Until then, Dockerfile development can be followed [on the synereo/dockerfiles Github repo](http://github.com/synereo/dockerfiles).

![image alt text](/img/uploads/docker.jpg)

### So, what can you actually do?

**1.** **You can set up a node** and interact with it both programmatically and via our UI.

* Take a look at [this blog post](http://blog.synereo.com/2015/03/17/specialk-kvdb/) to see more about the Scala language binding

* You can make calls into a node via http (see [this API](https://github.com/synereo/gloseval/blob/master/src/main/scala/com/biosimilarity/evaluator/spray/EvaluatorService.scala) lines 238 - 278)

* You can send messages into it via an AMQP provider (like RabbitMQ)

* You can point your browser to [http://localhost:9876/agentui/agentui.html?demo=false#](http://localhost:9876/agentui/agentui.html?demo=false#) and interact with our UI

* If you share the machine instance IP or have a name service for it, you can invite users to your node

![image alt text](/img/uploads/scala.jpg)

**2.** **You can connect nodes together**

* Right now, this involves modifying config files. If you want to do this, [let us know](http://slack.synereo.com) and we’ll explain the config file format to you -- the first one to document this process well gets a 15000 AMP bounty!

**3.** **Build new, amazing, decentralized apps.** All of the information and media can be uploaded and hosted on the distributed network. The app can operate without relying on any type of central server or authority.

* Want to build a new decentralized, distributed marketplace? This stack was made for that!

* Want to build a decentralized dating site? This stack was made for that, too!

![image alt text](/img/uploads/gui.jpg)

**4.** **Change the UI**

* Don’t like the look and feel of the Synereo UI? Change it! Break it! Make it better.

* We would love to hear what you did. If you come up with a good front-end design, we’ll pay bounties for that as well. (Join our [weekly community hangouts](https://www.facebook.com/events/842771732478375/) to get a feel of the UI we’re building in-house.)

**5.** **You can hack. You SHOULD hack.**

* The [GLoSEval API](https://github.com/synereo/gloseval) is just one of many, feel free to make up your own

* The API is built on top of a monadic API that exactly matches the semantics of feeds, and adds to it

* There’s a user model that builds a notion of quality of identity on top of the notion of channel, but you can make a different user model, or a different notion of identity.

In short - our stack is good to go! Get involved, and then let us know about your involvement; send us a pull request on github, chat about it in our [slack channel](http://synereonet.slack.com) or on [discuss](http://discuss.synereo.com), or just tweet @synereo. Making Synereo into a world-class service is too much for any one of us, but it’s just the right size for all of us.

