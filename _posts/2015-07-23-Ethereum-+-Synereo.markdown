---
layout: post
status: publish
published: true
title: Ethereum+Synereo=<3
date: '2015-07-23 2:37:02 +0200'
author: Greg Meredith
---
*TL;DR:* We’re using Synereo tech to help Ethereum flesh out their new Proof-of-Stake mechanism. 
Using our distributed protocol machine, we can create an implementation of the Ethereum protocol that we then run distributedly to probe and prod for possible issues. We can check what happens under load, when the network partitions, and effectively prove the protocol correct.  

Follow Synereo [CSO @leithaus](https://twitter.com/leithaus) to get real time updates on our progress and follow the development process as we interact with Etherium’s tech and team.

![image alt text](img/uploads/ethereum_dev_grant_tweet.jpg){: style="float: left; margin-right: 15px;"}


### Synereo has recently received a developer grant from Ethereum

Maybe you’ve even seen [the recent slide deck](https://github.com/leithaus/casper/blob/master/casper/docs/CasperInteraction.pdf). But what does it mean? How can Ethereum and Synereo be collaborating? What’s going on?

As we mentioned previously, Synereo’s entire backend is built on [a distributed protocol machine](https://github.com/synereo/agent-service-ati-ia/tree/master/AgentServices-Store). We use this both to define protocols, and verify that they work correctly, as well as to run them. 

Meanwhile, Ethereum is hard at work on a very cool [proof-of-stake protocol](http://www.slideshare.net/_hd/demystifying-blockchains) they call Casper. After reading Vlad Zamfir’s paper about Casper i was really excited to help make this happen, and i knew we had the technology to do that! (Btw, [Vlad also did some very Synereo-like work on Ethereum in the past](https://www.youtube.com/watch?v=vGTd1Bi7Jrc.))

![image alt text](img/uploads/casper_the_friendly_ghost.png){: style="float: left; margin-right: 15px;width: 80px;"}


### The method

So, here’s what we’re doing. First i’m getting a brain dump from Vlad on what Casper is. At the same time i’m teaching Vlad the [π-calculus](http://www.lfcs.inf.ed.ac.uk/reports/91/ECS-LFCS-91-180/) which is the mathematical model underlying our distributed protocol machine. (We were glad to hear other Ethereum folks are getting interested in this.) 

We’re capturing Vlad’s brain dump on Casper using interaction diagrams. Over the last 25 years or so i’ve discovered that interaction diagrams are an excellent mediating formalism. i’ve never had to explain how they work or what they mean in any discussion -- whether those discussions involved business types, cryptoanarchists, or propeller-head techies. i just start using them and -- just like comics -- people get the meaning immediately.

### The madness

However, as we discussed [in our white paper](http://www.synereo.com/whitepapers/synereo.pdf0), we can automatically turn those into the DSL we use for our distributed protocol machine. This gives us a reference implementation of the protocol that we can run distributedly to probe and prod for possible issues. 

We can also turn those into a format that we can feed into the [spatial logic model checker](http://ctp.di.fct.unl.pt/SLMC/) to check the protocol for a variety of properties, such as availability under network partition, and effectively prove the protocol correct.  

Additionally, we can also turn the interaction diagrams into a format that we can feed into [the stochastic π-machine](http://research.microsoft.com/en-us/projects/spim/) to investigate how Casper performs under various load conditions.

We figure this ought to really help understand Casper. Understanding of this kind for a protocol potentially this sensitive is vital. Blockchain technology is exciting. The potential is enormous, and no one wants this technology to succeed more than the Synereo team. We also have to be realistic: there’s a huge risk in putting global scale financial dependencies on these new technologies. That’s why we want to help Ethereum. 

### The big(ger) picture

This is also what we’re doing for all of Synereo’s protocols, such as the Reo calculation, and all the other protocols involved in the attention economy. [LivelyGig](http://blog.synereo.com/2015/04/15/livelygig-synereo/) is taking this same route. We’re doing the same for their gig-making and escrow protocols. In a decentralized world, it’s all about the protocol, baby. ;-)
