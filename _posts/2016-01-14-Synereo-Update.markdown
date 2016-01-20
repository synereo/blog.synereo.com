---
layout: post
status: publish
published: true
title: Synereo Weekly Update
date: '2016-01-20 08:00:00 +0200'
---

## Update Summary
<BR>
Special guest Dina Supino, UX and Product designer now working with Synereo. 

This week brings updates about: 

* Work on our Docker container / one-click installation 

* LivelyGig development update

* Work on Casper, the Proof-of-Stake protocol

* New collaborations with Backfeed, working on reputation and collaboration protocols, and

* weWOWwe, a Chinese sports-related social network starting to migrate functionality to rely on Synereo. 


## Contents in Brief

### [Watch the full Hangout](https://youtu.be/p-heibeelOc) <BR>
[0036 - Intro by Greg](https://youtu.be/p-heibeelOc?t=36) <BR>
[0335 - Dina introduces herself](https://youtu.be/p-heibeelOc?t=335) <BR>
*[0470 - What's design? A presentation by Dina](https://youtu.be/p-heibeelOc?t=470)* <BR>
*[0777 - Design challenges for open source projects](https://youtu.be/p-heibeelOc?t=777)* <BR>
[1189 - Response of Greg](https://youtu.be/p-heibeelOc?t=1189) <BR>
[1629 - Dor about cooperation with Backfeed and weWOWwe](https://youtu.be/p-heibeelOc?t=1629) <BR>
[1918 - Working as a community](https://youtu.be/p-heibeelOc?t=1918) <BR>
[2506 - Community takes up work](https://youtu.be/p-heibeelOc?t=2506) <BR>
[2636 - Code of the protocol](https://youtu.be/p-heibeelOc?t=2636) <BR>
[2916 - Largest AMP bounty so far given for Docker work](https://youtu.be/p-heibeelOc?t=2914) <BR>
[3050 - LivelyGig update by Ed](https://youtu.be/p-heibeelOc?t=3050) <BR>
[3196 - Casper update](https://youtu.be/p-heibeelOc?t=3196) <BR>
[3399 - Allan's involvement](https://youtu.be/p-heibeelOc?t=3399) <BR>
[3629 - Thanks](https://youtu.be/p-heibeelOc?t=3629) <BR>

## Detailed Notes

### [0036 - Intro by Greg](https://www.youtube.com/watch?v=p-heibeelOc&feature=youtu.be&t=36) <BR>
Special guest Dina Supino. Greg and Dor have been working closely with her on the design of the new UI and user experience of Synereo. 

### [0335 - Dina introduces herself](https://www.youtube.com/watch?v=p-heibeelOc&feature=youtu.be&t=335)<BR>
![image](http://i.imgur.com/0zQPJtH.jpg)
<BR>

[Dinasuarus](http://dinasaurus.com) 
[Linkedin](https://www.linkedin.com/in/dinasupino)
[FB](https://www.facebook.com/dina.supino?fref=nf)

I'm a UX designer, 10 years experience. My latest project was MS Azure. After that we've been travelling the world for the last couple of years. It's really been going around and looking at cultures and learning about how people think in all of these different countries. Most recently we've just got a house that we're going to move in Tuesday after the hang out at the base of the mountain here in New Zealand.
 
![image](http://i.imgur.com/mKYRLMI.jpg)
<BR>

### *[0470 - What's design? A presentation by Dina](https://youtu.be/p-heibeelOc?t=470)*
If you wanna help with Visual/Graphic Design, ... come forward. That's always great! First we need product design guidelines, the typography for making this entire product. Kind of making things beautiful and clean, and that work.

UI design is the process of creating user interfaces that balance technical functionality and visual elements. We need UI wireframes, prototypes, storyboards. Basically working through kind of the underpinnings of a product.

Content design goes back to the persona of the very specific users who are reaching out to us and keeping that communication channel on their way link.

Content writing.
Content writers will define rules for a voice. So this product is based on its brand and its users. It’s friendly and very lightly technical.

Information architecture creates a navigational tree and kind of a higher level of order for the whole product.

User experience. 
Designers need to kind of have a little bit of all of the aforementioned aspects but they're combining into a higher level look. It’s necessary to understand how to visualize advanced concepts, like what you would see in psychology and sociology.

Design thinking is about making the design implementation-free. Keeping yourself free from the technology.
 
![image](http://i.imgur.com/ooLVHcu.jpg)
<BR>
 
### *[0777 - Challenges for open source](https://youtu.be/p-heibeelOc?t=777)*
People have a great idea based on tech and the whole experience is based on that. It's difficult for design when the underpinnings already have been completely set. 
If you first focus on the goals then all sorts of different solutions come up. Then you can find the right one that really flows perfectly for the user. And that's why design needs to do that that process, out in front of the development input.

The nice thing is that we have a pretty engaged community that is pretty happy to give feedback.

If you have examples of novel UX made by open source project please put them down in the slack channel #design. 

![image](http://i.imgur.com/AV4aBaM.jpg)

There have been some critics on Synereo's open source based and community based approach. But [Christopher Alexander] (https://en.wikipedia.org/wiki/The_Timeless_Way_of_Building), (A Pattern Language, A Timeless Way of Building, The Nature of Order) has a different view on this.
A blend of course is always going to work a bit better. Laying down some fundamentals that are pretty strong and then letting the community build upon that. 
<BR>

![image](http://i.imgur.com/8wzLPfD.jpg)

Community feedback helps with the user testing issue.
Feedback is OK but it is informative for a designer, otherwise work gets never done. 
<BR>
![image](http://i.imgur.com/cgqAsEB.png)
<BR>

You have a [designers paradox](https://youtu.be/p-heibeelOc?t=1102) if feedback is constantly flowing instead of feedback that is ordered into purposed based points along the process.
![image](http://i.imgur.com/Jrc46cc.png)

Dina says that it's very important to define a product vision and she will cover it next week.
<BR>

### [1189 - Greg](https://youtu.be/p-heibeelOc?t=1189) points to his slides about [Reactive Media](https://drive.google.com/open?id=0BwX0krsxHncTbXpsd3BhcEtZNjA)
They are a language of concepts, capabilities and capacities, that people can utilise to rapidly put together user experiences but that also directly maps to the technology and the math. Recently we talked about channels "@" and labels "#". And that this could be used for the monitoring of the nodes. Since this is a decentralised network, users have to stand up their own nodes. You as administrator need that your node talks to you in a meaningful way. The social feed mechanism of Synereo can handle such things. You can also use it for monitoring the economic situation, i.e. your wallet that is associated with transactions.

So these principles have to translate into a comprehensible experience for the user. 

We have to find out what the group thinks about what to value, how they want to value it and what it means for individual reputation. And that has to be part of the user experience as well.

### [1629 - Dor about cooperation with Backfeed and weWOWwe](https://youtu.be/p-heibeelOc?t=1629)

We are cooperating with [Backfeed](http://backfeed.cc), founder is Matan Field, who was the founder of the rideshare company [La’Zooz](http://lazooz.org) and Primavera De Filippi, she was involved with [Ethereum](https://www.ethereum.org). Their aim is to create a reputation system for centerless coordination. There are a lot of similarities. They have a few nice pilots with chess games, where the entire community decides on the best move to make. Until now they have been improving the protocols, but they rely on a centralised entity that keeps track of the reputation of the members. That's not what Synereo wants. In Synereo, each user has a limited and subjective view of the network, and that’s enough to form our attention and reputation economy. The network topology simply changes to accommodate the relationship of the different agents based on their behaviors, and so no outside/central entity is needed. 

We have been talking about the basic assumptions we make, about the design of the system and what it should be able to do. And it looks that they want to use Synereo's technology to implement their protocols. And it seems like we're going to merge our efforts.

### [1918 - Working as a community](https://youtu.be/p-heibeelOc?t=1918)

Also with [Coala](http://coala.global/), that hosts the [blockchain workshop series](http://blockchainworkshops.org) and Vlad of Ethereum we're talking about reputation systems.  We are organising a satellite workshop in New York in April 2016 and we hope to have Backfeed, Livelygig, Synereo there and groups that are interested in the "internet of things" because we believe that things also should enjoy a reputation. Synereo is trying to jumpstart community effort around reputation systems and smart contracts, in order to investigate the concerns involved.  

One of our investors is involved in a Chinese social network around the subject of sports. Uploading videos about soccer matches, analysis and so on. We're talking about including the reputation and reward system into this and to slowly think about moving the content to the distributed paradigm. The company wants then the users to be able to redeem their tokens for badges, t-shirts, meetings with star soccer players, and later on services on the greater Synereo network once there’s a possibility to exchange their tokens for AMPs and other currencies. This shows nicely how you can create a network of networks in terms of exchange of reputation or monetary value.

Another side project is a company that is in social networks and that is interested in the technology of Synereo. China is probably one of the most important markets for decentralisation technology. It's really critical there.

### [2506 - Community takes up work](https://youtu.be/p-heibeelOc?t=2506)

Dory (@nodes, @007) did some great work on the Docker problem. He was able to resolve the RabbitMQ interaction between two Docker servers. This is very exciting and that enables us to then aid data storage through Mongo to the doctor image.

The venue protocol. This makes it harder to do discovery in the network. If you know only the people that you're already connected with, how do you find new people to talk to? There's a need for people to find each other with respect to your network. That gives a place for a kind of broker in between. Livelygig needs this of course to match talented people with the demand for work.


### [2636 - Code of the protocol](https://youtu.be/p-heibeelOc?t=2636)
<BR>

![Image](http://i.imgur.com/0PWb2xQ.jpg)

<BR>
The protocol is in fact a few pages of code. A part that configures the behaviour, a part the sets the definitions, and a part that executes the protocol. In the configuration you can define what behaviour is launched when a node is launched. For example the feature "You need to be introduced in order to talk to this person." In the current interface you can drop a person icon onto another person icon. A message "Do you want to introduce these two people to each other?" pops up. And then it gives you the opportunity to send out a little introduction notice to each of them and then they are invited to connect to each other.

This approach of defining protocols gives a significant acceleration and in addition there are all kinds of advantages with respect to a formal verification and correctness of the protocol, service discovery, etc..

### [2916 - Largest AMP bounty so far given for Docker work](https://youtu.be/p-heibeelOc?t=2914)
<BR>

Dor expresses his appreciation for Dory. He's not only one of Synereo’s largest investors, a very passionate member in the community, but he also unblocked the creation of the Docker Image, with respect to the RabbitMQ. With this achievement it becomes very easy to set up a node for the Synereo network. So he's rewarded with a bounty of 50,000 AMPs, worth close to 500$ (highest bounty until now).

## So If you're a developer in Scala, have DevOps skills, or have other IT-related knowledge, you could earn also AMPs. Talk to us!

### [3050 - LivelyGig update by Ed](https://youtu.be/p-heibeelOc?t=3050)
The number of protocols we use for Livelygig is relatively small if compared with the complexity of the application. 
We've been working a lot on the user interface. Some of it is on the technological architecture that is needed, for example on Scala React.
And we've been building up various pop-ups. 
We are focused on getting an end to end story that we can demo. 




### [3196 - Casper update](https://youtu.be/p-heibeelOc?t=3196)
There’s been progress in converting the betting-cycle stuff into π-calculus interpretation. We do this because then we can work finally with SpecialK. There's growing consensus between Aaron Fisher, Vlad (Ethereum) and myself. You get a uniform treatment of network partition events as well as standard betting cycle behaviours. So the economic and security analysis
come into a single frame,  which is extremely powerful.
We've also done a code review of a proof-of-concept that was set up by Vitalik. It raised some interesting questions, because Casper takes a stance that's pretty much the opposite of Industry wisdom. Which is cool, because a lot of revolutionary protocols have done this also.

### [3399 - Allan's involvement](https://youtu.be/p-heibeelOc?t=3399)

He's very interested in what SpecialK can do as a platform and I have some specific experience that Livelygig can leverage. Allan refers to his company "Answer2" started in 2013. It’s basically turning questions and answers into a contest. The project was shot down because the term sheets of the funding were not alright. But the idea is still valid. Allan was introduced to Ed by an attorney who knows blockchain really well. And he has additional experience with the launch of [Safe.cash](https://safe.cash), a white label commissioned based blockchain based payment system for banks to create their own Paypal services and offer it to their clients. It uses dollars directly, not an alt-coin and the keys don't sit on the technology layer.  [See also](https://www.pehub.com/2015/09/safe-cash-payment-technologies-raises-1-12-mln/)

He hopes to bring that experience to SpecialK and LivelyGig in terms of launching a platform that people can use to build distributed apps with very little effort and very little code and focus on what their apps are really supposed to be doing.

### [3629 - Thanks](https://www.youtube.com/watch?v=p-heibeelOc&feature=youtu.be&t=3629)

Please read the Open questions for pitch deck](https://docs.google.com/document/d/1xdKayitmM60PCBRCmekiDc5XOcN62LIN-a9MvFQQRDs/edit?usp=sharing)

##That's all for this week!

