---
layout: post
status: publish
published: true
title: Synereo Weekly Update
date: '2016-02-10 08:00:00 +0200'
---

## Update Summary

This week Greg discusses the betting cycle within the Casper Proof of Stake protocol and explains the technology choices underlying the Synereo platform. The community discusses issues of governance and how project management can be implemented within the Synereo application itself.

![Casper Betting Cycle](http://cdn.loc.gov/service/pnp/fsa/8d41000/8d41400/8d41412r.jpg)<br>
Early research on Casper Proof of Stake[^1].

## Contents in Brief

### [Watch the full Hangout](https://youtu.be/2x9X-wVvarQ)

[01:13 --- Quick updates](https://youtu.be/2x9X-wVvarQ?t=1m13s)<br>
[12:14 --- Casper (Proof of Stake)](https://youtu.be/2x9X-wVvarQ?t=744)<br>
[23:49 --- Service Discovery on a Sharded Blockchain](https://youtu.be/2x9X-wVvarQ?t=23m49s)<br>
[28:22 --- Ambassador Role](https://youtu.be/2x9X-wVvarQ?t=28m22s)<br>
[37:58 --- Governance](https://youtu.be/2x9X-wVvarQ?t=37m58s)<br>
[56:50 --- Technology Choices](https://youtu.be/2x9X-wVvarQ?t=56m50s)<br>
[1:08:34 - Bi-Weekly Core Community Meetings](https://youtu.be/2x9X-wVvarQ?t=1h08m34s)<br>

## Detailed Notes

### [01:13 - Quick updates](https://youtu.be/2x9X-wVvarQ?t=1m13s)

* [LivelyGig](http://livelygig.com/): Ed Eykholt and Navneet Suman
 are working on creating an escrow protocol and log-in for their decentralized marketplace for Freelancers.

* Greg has been talking with [weWOWwe](http://wewowwe.com) about different ways that Synereo could be set up for their users.

* We welcome Ty Simpson to the hangout. He is interested in open-sourced decentralized social networks for use in open governance and intentional communities.

* Dory (@nodes, @007) has made good progress with the docker image. He has built specialK, the user (IA) model, and is now adding glosseval. A setup guide is coming together in the following [Blog post](https://discuss.synereo.com/t/node-testing-setup-guide/66358)

### [12:14 - Casper (Proof of Stake)](https://youtu.be/2x9X-wVvarQ?t=744)<br>
Greg has been working with [Aron Fischer](https://twitter.com/mathsguy), [Vlad Zamfir](https://twitter.com/VladZamfir), and the Ethereum team to formalize the betting cycle behind Casper.

Greg demonstrates with a model tetrahedron how the collection of probability distributions can be represented as a k-dimensional simplex structure. An updated bet by a validator is non-punishable if it traces a history through this space toward convergence onto a vertex.

(I tried to find an illustrative diagram...)

![simplex](http://i.stack.imgur.com/6fESJ.png)
Trajectory of bets converging on consensus within a 3-simplex[^2].
<br><br>

#### Recent Casper Videos by Greg:

* [Casper - Betting cycle convergence](https://youtu.be/la45Qu20nX0)<br>
Streamed live on Feb 3, 2016

* [Casper Research Team Standup](https://youtu.be/2WulGGVIRcs)<br>
Streamed live on Feb 1, 2016<br>
Sharding and causal dependencies

* [Casper Research Team Standup](https://youtu.be/adunESrJTSk)<br>
Streamed live on Jan 25, 2016<br>
This week's standup topics include more on namespace sharding and types, as well as a discussion of Martin's Ambient-based proposals.

### [23:49 - Service Discovery on a Sharded Blockchain](https://youtu.be/2x9X-wVvarQ?t=23m49s)

Synereo provides a decentralized content distribution network by utilizing [SpecialK/KVDB](http://blog.synereo.com/2015/03/17/specialk-kvdb/) decentralized storage and transactional semantics. This same architecture could be used to provide service discovery for accounts residing in a sharded blockchain such as that proposed for Ethereum 2.0.

### [28:22 - Ambassador Role](https://youtu.be/2x9X-wVvarQ?t=28m22s)

Jed presents a new role available for outgoing community members wanting to help us out:

~~~
NEW ROLE ANNOUNCED: AMBASSADOR 

In response to the amazing growth and activity we’ve seen in our community, Synereo is announcing a new role: the Ambassador. 

Ambassadors are responsible for to going out into various communities across the web and acting as a liaison between them and Synereo. Ambassadors will play a key role in helping the early network establish partnerships with communities abroad.  

As Ambassadors, members will reach out to other community leaders and engage them about Synereo. In simple english, the Ambassadors will share links in communities that want them, and actively reach out to the leaders of these communities. Your job will be to establish a relationship with a few key communities, and get them the news they need when it works for them. This isn’t about click-farming, far from it. This is about actually valuing people and helping communities work towards mutual goals, and playing a valuable role in the communities you are active in. 

Payouts for this role will be made on a weekly basis, and are based on reaching target goals within your community. Ambassadors will stay in touch with the community manager, and work together to help coordinate. The reward is `$15 to $50` dollars worth of AMPs per week, based on scope of work. Bonuses for extra sharing are available. 

This role is monumental in helping Synereo as we make our push to build a truly decentralized tool that will not only help other partners create decentralized applications, but build a strong community around decentralized cultures. It’s more than just an app, we are working with others in the greater community to build a whole new way interacting on a global scale. 

To apply, please send an email to hello@synereo.com.

Priority will be given to people who are already active participants in the hangouts/community and those who attach a sample of their writing - a post on a forum, a blog post, or anything showing that you can communicate with others in writing in an open and friendly way. 


The Synereo Team

Be Part of the Solution
~~~

### [37:58 - Governance](https://youtu.be/2x9X-wVvarQ?t=37m58s)

LiveleyGig is able to create Synereo based feeds to post and manage projects for Freelancers. Similarly, we would like to conduct our project Governance from within Synereo itself. The features that we need include the ability to track tasks, issues, backlogs, bounties, developer skills, etc. As we coordinate projects in [Taiga](https://tree.taiga.io/project/synereo-synpm/wiki/home), please try to identify workflows that we can build into Synereo.

### [56:50 - Technology Choices](https://youtu.be/2x9X-wVvarQ?t=56m50s)

Synereo's core technology is the applied [π-calculus](π-calculus), an extensively vetted mathematical approach for formally modelling concurrent systems and process interaction. It informs our architecture and programming model. 

*Trust the math*{: style="color: red"}. As an open-source project, anyone is welcome to inspect our code and the mathematical models on which it is based.

#### Synereo Front-End
These are the 'Front-end' technologies being implemented by LivelyGig and Synereo: 

* [Scala.js](http://www.scala-js.org/)
* [React.js](https://facebook.github.io/react/)
* [Diode](https://github.com/ochrons/diode)

You can see how for yourself how the pieces fit together by visiting [LivelyGig's GitHub](https://github.com/LivelyGig/ProductWebUI/tree/master/ProductWebScalaReact).

#### Synereo Tech Development Videos
Greg recorded his recent meetings with [Gary Stephenson](https://plus.google.com/110716450918614417772), the Australian developer mentioned in this and last Wednesday's Hangout. More such videos will be forthcoming...

* [(Unlisted) Synereo Developer's Session](https://youtu.be/vLEXoi1wSbI)<br>
Streamed live on Jan 31, 2016

* [Synereo Developer node setup continued](https://youtu.be/4ieXoBeWoIs)<br>
Streamed live on Feb 10

* [SpecialK build](https://youtu.be/YXj5IWZk9PM)<br>
Streamed live on Feb 3, 2016<br>
We look at how to build SpecialK on an ubuntu image.

### [1:08:34 - Bi-Weekly Core Community Meetings](https://youtu.be/2x9X-wVvarQ?t=1h08m34s)

In addition to the weekly Community Hangout every Wednesday, we will soon be setting up 15 minute bi-weekly 'stand-up' meetings for any core community members who wish to share updates as to what each of us is working on. These will likely be hosted on a [Jitsi Meet](https://jitsi.org/Projects/JitsiMeet) server.

That's all for this week!

## If you like what we're creating, send some bitcoin to 18c1en55Cs2jBgBT2LTAiK9M81vMUmXmxw
![18c1en55Cs2jBgBT2LTAiK9M81vMUmXmxw](http://i.imgur.com/jlHprSv.jpg)

[^1]:Washington, D.C. Walter Spangenberg (holding the pointer) giving a demonstration in geometry class at Woodrow Wilson High School, image from US Library of Congress, Call Number: [LC-USW3- 039642-D [P&P]](http://www.loc.gov/pictures/item/owi2001037245/PP/)

[^2]:[cc by-sa 3.0](https://creativecommons.org/licenses/by-sa/3.0/) image from [Stack Exchange question](http://mathematica.stackexchange.com/questions/2099/plotting-a-set-of-trajectories-not-a-vector-field-in-3d) by [István Zachar](http://mathematica.stackexchange.com/users/89/istv%C3%A1n-zachar)
