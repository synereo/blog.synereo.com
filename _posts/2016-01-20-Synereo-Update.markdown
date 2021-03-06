---
layout: post
status: publish
published: true
title: Synereo Weekly Update
date: '2016-02-02 08:00:00 +0200'
---

## Update Summary
<BR>

This week, we talked about the latest bitcoin controversy. We discussed the claims raised by core developers on both sides of the argument, and debated potential solutions to problems of centralization of mining and governance. 
Governance of decentralized projects is difficult! Synereo wants to implement centerless-coordination mechanisms right from the start.

LivelyGig is progressing on its UI. Code reviews clean a lot of clutter through the magic of functional programming in Scala. weWOWwe, a social network for sport, is on board and work has begun with them to provide them with some of Synereo’s functionality. 

Additional dev grants from Ethereum for the work on Casper, the new Proof of Stake protocol Greg is leading the design for, are approved. 

Scala developers are most welcome to join our coding efforts and will be *highly rewarded!* Also, if you aren’t a Scala developer and you want to help us grow, find us on our [slack channel](http://synereo.slack.com)! 

![image](http://i.imgur.com/355VejM.jpg)

## Contents in Brief <BR>
<BR>

### [Watch the full Hangout](https://www.youtube.com/watch?v=A0JYkKLl830) <BR>
[00:58 - Mike Hearn & Bitcoin news](https://youtu.be/A0JYkKLl830?t=3m58s) <BR>
[03:10 - Ethereum dev grant](https://youtu.be/A0JYkKLl830?t=190) <BR>
[13:01 - Dor: Bitcoin is here to stay](https://youtu.be/A0JYkKLl830?t=13m1s) <BR>
[16:30 - Market forces in Proof of Stake](https://youtu.be/A0JYkKLl830t=16m30s) <BR>
[20:05 - Synereo governance and centerless collaboration](https://youtu.be/A0JYkKLl830?t=20m05s) <BR>
[29:00 - LivelyGig update](https://youtu.be/A0JYkKLl830?t=29m00s) <BR>
[32:00 - Code review of the UI](https://youtu.be/A0JYkKLl830?t=32m00s) <BR>
[38:48 - Dor's update, Backfeed protocol can be implemented on Synereo tech](https://youtu.be/A0JYkKLl830?t=38m48s) <BR> 
[42.45 - About Membranes as delineators in groups](https://youtu.be/A0JYkKLl830?t=42m45s) <BR>
[49.00 - About AMP Wallets](https://youtu.be/A0JYkKLl830?t=49m00s) <BR>
[52.17 - Scala developers needed!](https://youtu.be/A0JYkKLl830?t=52m17s) <BR>
[53:28 - Bring us in contact with Bernie Sanders](https://youtu.be/A0JYkKLl830?t=53m28s) <BR>

## Detailed Notes <BR>
<BR>

### [03:10 - Ethereum dev grant](https://youtu.be/A0JYkKLl830?t=190)<BR>
Based on conversation with Wendell Davis (Ethereum), the accorded grant of last year will be paid out and it is likely that Synereo will get another grant for the progress that has been made on Casper.

### [03:58 - Mike Hearn & Bitcoin news](https://youtu.be/A0JYkKLl830?t=235) <BR>
Greg wanted to get the conversation kicked off with a little bit from the recent news flurry on the departure and out-going message by Mike Hearn, of Bitcoin.  (Ref: [Mike Hearn](https://medium.com/@octskyward/the-resolution-of-the-bitcoin-experiment-dabb30201f7#.8gusjxgnp)), (Ref Responses: [Reddit citboins](https://www.reddit.com/r/Bitcoin/comments/4151ng/the_mike_hearn_show_season_finale_and_bitcoin/), [Greg Slepak](https://fixingtao.com/2016/01/point-by-point-response-to-mike-hearns-final-bitcoin-post/), [Henry Brade](https://medium.com/@Technomage/bitcoin-has-now-died-89-times-274df173c246#.lchu5jdue), [Ryan Shea](https://medium.com/@ryanshea/the-scaling-announcement-bitcoin-core-should-have-made-146790f755df#.781y6l5j5))

Ed began by saying that Mike is a very bright guy, and a loss for Bitcoin momentum.  He thought that Mike had sealed his fate when he implemented the hard fork in XT, and if you remove all the personalities from this, the Bitcoin ecosystem and community still has a problem with what decentralized governance means.  The Bitcoin foundation has largely failed, and has a black eye.  At the [Scaling Bitcoin Conference](https://scalingbitcoin.org/hongkong2015/#presentations), from what he saw,  the biggest problem is how to make decisions.

In all of these decentralized projects, including Synereo, and LivelyGig, to the extent that those become open source from the community's perspective, we need to address how we make group decisions.  It's a reminder that we have a governance challenge.
 
Greg agreed, adding that it's a sociological problem, not a technological one.  The Bitcoin story is a learning experience, and as an analogy points out that HTTP is a stupid protocol, designed by the wrong people.  But it served as an entry point into larger communities of the corporate world, and if it had been better, it may not have made it - using [Gopher](https://en.wikipedia.org/wiki/Gopher_%28protocol%29) as an example.  HTTP is a "failure" too, in the sense that it has had to change & evolve along the way, in order to meet the changing needs of that market.
  
He also touched on the difficulty of explaining these new, advanced protocols like Casper, which are replacing the older Bitcoin protocols, and it took 5 months of explaining for him (who is not an initiate in these matters) to get it.  Nonetheless, he believes that the technological problems can be solved; the sociological ones are more "interesting".  This is one reason why we are operating with transparency.
 
### [13:01 - Dor: bitcoin is here to stay](https://youtu.be/A0JYkKLl830?t=13m1s)<BR>
Dor thinks that each time someone claims that bitcoin is dead, it actually is becoming stronger. This claim happened now 89 times. It gets media attention and more people become interested. And they become more convinced that bitcoin is here to stay. He thinks many of the things Mike Hearn says are not really relevant to what's going to happen with bitcoin core, but that he does bring up some valid concerns. One thing is interesting with regards to proof of work. The Chinese have the most processing power and therefore centralization is starting. They have a financial interest in keeping the block size small, because their network handles better small block sizes. And therefore they have more chances to validate blocks and earn the 25 bitcoin reward. Dor raises the question about whether Proof of Stake will be able to avoid these kind of problems.

### [16:30 - Market forces in Proof of Stake](https://youtu.be/A0JYkKLl830?t=16m30s)<BR>

[![image](http://cointelegraph.com/images/720_aHR0cDovL2NvaW50ZWxlZ3JhcGguY29tL3N0b3JhZ2UvdXBsb2Fkcy92aWV3L2UwODQxNmNiY2Y5YmNlYjBhYTc0NDg4Y2RhZGE4YzJlLnBuZw==.jpg)](http://cointelegraph.com/news/113157/proof-of-work-proof-of-stake-and-the-consensus-debate)

With Proof of Stake, the block validators may come and go. The market forces within PoS are different with respect to validators. Those businesses that have invested a lot in mining gear (like in speedy ASICs) for PoW don't have a particular advantage with PoS. That means that there is no centralization because one has the fastest mining gear. An issue with PoS is whether or not there is obfuscation of the ordering of transactions in blocks. When there is no obfuscation of the transactions that are included blocks, then there will be a market around the ordering of transactions. If you compare it to the current banking systems, then banks order transactions to maximize their fees. Possibly, having a market allows for a wider visibility of the ordering of transactions and better control on the part of other interests, not just the banks. A market may also starve out certain types of computation, however. That's kind of troubling!

### [20:05 - Synereo governance and centerless collaboration](https://youtu.be/A0JYkKLl830?t=20m05s)<BR>
Another lesson is that is hard to have a decentralized system with centralized control especially when there's censorship on the main channels of communication related to Bitcoin Talk amd Reddit. Dor hopes that Synereo offers a superior experience with a decentralized communication platform. A mechanism will be baked in for voicing your opinion, collaborating on proposals and measuring your reputation. This should allow for better governance.

Ed says that we have to engage with studies in this field, [see](http://portal.uc3m.es/portal/page/portal/dpto_economia_empresa/home/seminars/Previous_years/Seminars_2006-2007/Ferraro_GOPC_9-8-06_000.pdf)
He asks how release management is done, when Synereo has a lot of nodes. You could then maybe send releases out as data on the network, but it would still need a voting system with signatures.

[![image](http://i.imgur.com/O6HywHX.jpg)](http://codev2.cc/download+remix/Lessig-Codev2.pdf) 

[Lessig, - Code is law](http://codev2.cc/download+remix/Lessig-Codev2.pdf)  maybe of interest as well. Lessig has been thinking about these issues since the '90.s. And we are building a censorship resistant public information utility that allows for essential transactions, like ownership of a house. Therefore the code has to be open and reviewed by a lot of eyeballs not only developers but also the common folks need to know what the code is doing and what the concerns are around that code. See also [ZeroMQ](https://www.youtube.com/watch?v=36bKE_JsHZs): Our decentralized future. And [Taiga](https://taiga.io/support/) for decentralized project management
[![image](https://opensource.com/sites/default/files/styles/image-full-size/public/images/business/BUSINESS_orgchart1.png?itok=DGsp6jB5)](https://opensource.com/business/14/10/taiga-open-source-project-management-tool)

One advantage of the discussions around Mike Hearn is that all the proposals and problems have been summarized and explained.

We need a kind of side project that shapes the governance around Synereo.

### [29:00 - Livelygig update](https://youtu.be/A0JYkKLl830?t=29m00s)<BR>
Ed continues to work on the user experience and an end to end demo: How do the employer and freelancer meet each other? How do they form a contract, pay into escrow, complete the work and how is feedback provided about how that gig went. Techniques are: [scala.js](http://www.scala-js.org) that updates a portion of the DOM. The connection between the client and server needs to work through the architecture stack, Diode. It's a better way than the Model-View-Control model. See: [Diode framework](http://ochrons.github.io/diode/) and [Flux](https://github.com/facebook/flux).

[![image](http://ochrons.github.io/diode/images/architecture.png)](http://ochrons.github.io/diode/)<BR>


### [32:00 - Code review of the UI](https://youtu.be/A0JYkKLl830?t=32m00s) <BR>
Greg did a code review and emphasized the importance of type in Scala.js. It was, for example, not clear what was cast into a particular parameter. By just looking at the type, the problem could easily be solved. This you cannot do in JavaScript but in Scala.js you can. 

![image](http://i.imgur.com/hV8rGjg.jpg)

The importer-code needed a lot of re-factoring. We added just the type save configuration management code and skipped hard coded resources. The importer defines in a .json file, a model data set with some users, labels and connections, that allows for a quick demo or test configuration. The resources include the data file and also the servers where it registers the users and creates labels and posts. 

You can now set up the servers and ports you're talking to and the email validation. We increased performance by splitting the import up in chunks: first make the user, then the labels, and then make the connections.

This allows for fine grained testing, wiring it up to the UI so that you get a page where you raise users for test scenarios.

### [38:48 - Dor's update, Backfeed protocol can be implemented on Synereo tech](https://youtu.be/A0JYkKLl830?t=38m48s)<BR> 
[![image](http://i.imgur.com/5jC1upa.jpg)](http://football.wewowwe.com)  Synereo signed an agreement with [weWOWwe](http://football.wewowwe.com) , a sports-related social network. Their users express their experiences about sports. Depending on how such a message is perceived, they get a kind of reputation token. These tokens can be exchanged for various rewards, like a meeting with one of the players or sports items in a market. They will use Synereo for measuring the response that is coming out of the content delivery networks. They collect the information and ship it off to Synereo, which is storing on behalf of the user, updated versions of the responses to their posts. Synereo keeps track of the cryptographic tokens and tracks the response of various users of social networks.

We also made a breakthrough in integrating [BackFeed's](http://backfeed.cc) inter-subjective protocols for reputation, that may also later be used for a governance model. Finally, there was a kind of common language to understand each other :-) They aimed for a kind of dynamic group creation through one smart contract and that suggests some centralization. 

### [42.45 - About Membranes as delineators in groups](https://youtu.be/A0JYkKLl830?t=42m45s) <BR>
So Greg also explained the sister of [π-calculus](https://en.wikipedia.org/wiki/%CE%A0-calculus), the [Ambient calculus](https://en.wikipedia.org/wiki/Ambient_calculus). It's about nested membranes, and a membrane can define group membership. Those agents that are inside the membrane are part of the group and those who are outside of the membrane are not part of the group.  Ambient gives you a certain programmability of groups; you can create new membranes, it allows agents to enter and leave a membrane, and you can dissolve a membrane. 
[Luca Cardelli](https://en.wikipedia.org/wiki/Luca_Cardelli) realized that the programmability of membranes was even more important then he thought. He found decentralized tools for programming and creating membranes. This model is much more apt to what Backfeed wants to realize.

[![image](http://math.lanl.gov/~yi/lipid/membrane.jpg)](https://en.wikipedia.org/wiki/Ambient_calculus)
 
### [49.00 - About AMP wallets](https://youtu.be/A0JYkKLl830?t=49m00s)<BR>
At the moment the most convenient wallet for AMPs is the [OmniWallet](https://www.omniwallet.org/), but for LivelyGig a wallet has probably to be developed. Within Synereo you have to be able to manage your AMPs as well. 

[![image](https://www.omniwallet.org/assets/img/logo-beta.png)](https://www.omniwallet.org/about)
<BR>

### [52.17 - Scala developers needed!](https://youtu.be/A0JYkKLl830?t=52m17s)<BR>
If you know Scala developers, please bring them on board. They will be rewarded with AMPs for their work. It's a cutting edge technology in a rapidly growing space, so this is the time to get in. Even if you want to learn this functional programming language, then you're welcome.

[![image](http://ncredinburgh.com/img/blog/henry_coles/scala-logo.gif)](http://www.scala-lang.org)

### [53:28 - Bring us in contact with Bernie Sanders](https://youtu.be/A0JYkKLl830?t=53m28s)<BR>
The [Bernie Sanders](https://berniesanders.com/issues/) campaign needs to get up to speed with blockchain technology and how they will impact society moving forward. It's about addressing the inequality of income and wealth.
<BR>
[![image](https://berniesanders.com/wp-content/uploads/2015/08/20150817_Charts_2-2.png)](https://berniesanders.com/issues/income-and-wealth-inequality/)
<BR>


That's all for this week!
<!--se_discussion_list:{"bW5ylGUUtfitwZSsijG37wYT":{"selectionStart":23,"selectionEnd":72,"commentList":[{"content":"what do you mean with 'uphold'?"},{"content":"It needs another word for something like drama"},{"author":"Lapin7","content":"Do you see this?"},{"content":"yes"},{"author":"Lapin7","content":"Aha I see your comment :-)"},{"author":"Lapin7","content":"This is the only chat possibility, but that's kind of slow. Maybe google docs is better"}],"discussionIndex":"bW5ylGUUtfitwZSsijG37wYT"}}-->
