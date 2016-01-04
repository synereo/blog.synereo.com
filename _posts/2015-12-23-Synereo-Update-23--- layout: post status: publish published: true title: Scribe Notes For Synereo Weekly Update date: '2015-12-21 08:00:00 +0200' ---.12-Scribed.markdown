---
layout: post
status: publish
published: true
title: Scribe Notes For Synereo Weekly Update
date: '2016-01-04 08:00:00 +0200'
---

## Update Summary
![Synereo Hangout - Greg](http://i.imgur.com/vUouZsY.jpg?1)

Recently, our Chief Science Officer, Greg Meredith, wrote a paper in which he explained operations on the blockchain in terms of classical linear logic: 
[Linear Types Can Change the Blockchain](http://arxiv.org/abs/1506.01001). What was left out were details on how 'consensus' is reached in this type of blockchain. This week, Greg offers the mathematical underpinnings of blockchain consensus under the 'Proof of Stake' protocol he has been developing and that will **replace Ethereum’s existing blockchain [in their next update](https://blog.ethereum.org/2015/12/24/understanding-serenity-part-i-abstraction/).**

Later in the hangout, Greg discusses the concept of identity. He suggests using the mobile process calculi as a framework to describe identity in terms of a history of transactions over a collection of channels over time. This is an approach that will allow us to realize the benefits of a blockchain while also relying on the trust created in the Synereo social network. A sort of hybrid between the standard Bitcoin approach and the Gateway-based Ripple approach, relying both on a chain of custody (timestamped ledger) as well as on Synereo reputation. This paradigm should **permit this neo-blockchain to scale in throughput without issue and without encumbering nodes with huge, resource-intensive global ledgers.**

All AMPs will be migrated to this new tech, of course, if and when this happens.


<BR>


## Contents in Brief

### [Watch the full Hangout](https://youtu.be/mz-HXpTj_yw?t=272) <BR>
[06:07 - LivelyGig Updates](https://youtu.be/mz-HXpTj_yw?t=367) <BR>
[09:34 - ‘Decentralization’ gaining attention](https://youtu.be/mz-HXpTj_yw?t=574) <BR>
[11:39 - Synereo Node Management](https://youtu.be/mz-HXpTj_yw?t=699) <BR>
[17:52 - Proof of Stake / Blockchain Geometry](https://youtu.be/mz-HXpTj_yw?t=17m52s) <BR>
[18:09 - Composable Blockchain](https://youtu.be/mz-HXpTj_yw?t=1089) <BR>
[53:40 - Iterated Function has an attractor?](https://youtu.be/mz-HXpTj_yw?t=3220) <BR>
[56:13 - Identity](https://youtu.be/mz-HXpTj_yw?t=3373) <BR>


<BR>

## Detailed Notes

### [06:07 - LivelyGig Updates](https://youtu.be/mz-HXpTj_yw?t=367) <BR>

Ed presented a talk at Inside Bitcoins [Blockchain Agenda](http://insidebitcoins.com/san-diego/2015/agenda) event:

[Smart Contracts: Enabling New Work-Life Culture](http://www.slideshare.net/eeykholt/smart-contracts-enabling-new-worklife-culture)

![LivelyGig Architecture](http://i.imgur.com/kgrLk31.png)

Partial videos from that presentation, in 3 parts: 

1: [https://youtu.be/nB4oTjZYQB0](https://youtu.be/nB4oTjZYQB0)

2: [https://youtu.be/0L0sRDVSRSE](https://youtu.be/0L0sRDVSRSE)

3: [https://youtu.be/vRYMx6jN6Tg](https://youtu.be/vRYMx6jN6Tg)

LivelyGig welcomes a new team member, Ryan, who will be working in market strategy and research. Lately Ed, Monica, and Navneet have been mocking up the user interface to demo for investors.

Nirvanic, in India, has been working on user Registration, validation, and log in. Help is needed to interface with GloSEval.




### [09:34 - ‘Decentralization’ gaining attention](https://youtu.be/mz-HXpTj_yw?t=574) <BR>

Decentralization technology is happening everywhere: FinTech, markets, storage, voting systems, social networks, etc. We will see the launch of many new trustless infrastructures and institutions in 2016!  The market is becoming more aware of the concepts, and there’s less need to have to explain what the benefits are. We can get right down to discussing uses.

### [11:39 - Synereo Node Management](https://youtu.be/mz-HXpTj_yw?t=699) <BR>

Management objects such as logs and diagnostics can be viewed as posts and streams. They can be filtered in the same fashion as other Synereo objects.  This will give a unified experience for users.

### [17:52 - Proof of Stake / Blockchain Geometry](https://youtu.be/mz-HXpTj_yw?t=17m52s) <BR>

Greg presented on the geometry of Blockchain by discussing the Proof of Stake protocol as a ‘trace’:    
![The Geometry of the Blockchain](http://i.imgur.com/Fcbz6AQ.jpg)

This mathematical object allows us to set rules for the blockchain, and do so in a ‘tinker-toy’ fashion. It is scalable, and can be set up piece by piece - again, in the decentralized way.


### [18:09 - Composable Blockchain](https://youtu.be/mz-HXpTj_yw?t=1089) <BR>

The blockchain does enjoy a braided monoidal structure and when you impose the transaction reordering constraint at the level of blocks you get a symmetric monoidal structure.

The betting cycle is a trace on the symmetric monoidal structure. The betting cycle, internally, is an iterated function system. So here we get internal laws about how betting strategies have to be structured. We get external laws, in terms of the traces, about how betting strategies have to be structured. The relationship of the trace monoidal category to the linear types idea is that the trace monoidal category gives us an interpretation of linear logic. The two fit together and support each other.

As evidence to this argument, there was a [paper](http://arxiv.org/abs/0803.2429) published recently that describes double entry bookkeeping in terms of a particular bi-category structure, similar to the monoidal structure that we are looking at here. There are the beginnings of consensual validation in the category theory community.

### [53:40 - Iterated Function has an attractor?](https://youtu.be/mz-HXpTj_yw?t=3220) <BR>

[Martin Becze](https://twitter.com/null_radix) from Ethereum asked for clarification as to where the attractor comes from. Greg explained that the betting strategies must have a particular internal structure in order to assure that there is an attractor. [The following paper](http://www.ams.org/journals/proc/1992-116-01/S0002-9939-1992-1132850-6/) is cited: (Attractors of Iterated Function Systems)

**Abstract**. *In this paper, the question of which compact metric spaces can be
attractors of hyperbolic iterated function systems on Euclidean space is studied.
It is shown that given any finite-dimensional compact metric X , there is a
Cantor set C such that the disjoint union of C and X is an attractor. In the
process, it is proved that every such X is the Lipschitz image of a Cantor set.*

### [56:13 - Identity](https://youtu.be/mz-HXpTj_yw?t=3373) <BR>

There are several startups applying machine learning to create 'identities' based on a user's transaction history. Greg suggests using the mobile process calculi as a framework to describe identity in terms of a history of transactions over a collection of channels over time. The notion of identity begins with channels, but channels themselves do not provide identity.

Several subtleties were discussed. Individual identity is different from institutional identity. Amazon, for instance, is an institutional identity represented by many different employees at different locations and times. Another subtlety comes from context ie. 'promises made at the pub vs. promises made at the alter'.

### Addendum: Synereo Social Contracts

The following example was used to walk through a type of social contract in Synereo. In this case, a ‘verification protocol’. This was written up previously in a Synereo [blog entry](http://blog.synereo.com/2015/03/06/social-contracts-pt-ii/).

![Interaction Diagram](http://i.imgur.com/I0Bgacj.png)

How particular agency is able to fulfill particular roles can be described in terms of social contracts. Greg says the relationship of role to identity is the next step in the notion of identity... Perhaps we can observe a continuum stretching from individual roles all the way to strong 'identity'.
<BR>

That's all for this week! 


