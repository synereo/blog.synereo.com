---
layout: post
status: publish
published: true
title: Scribe Notes For Synereo Weekly Update
date: '2015-12-13 08:00:00 +0200'
---

## Development Update
[As we continue our tradition of summarizing the updates of our weekly hangout](http://blog.synereo.com/2015/12/02/new-bounty/), here are the highlights of this week - courtesy of our dedicated community members, @lapin7, @drbloom and @malthusjohn. Thanks, guys!
<BR>

This week brings updates from Greg's participation in a blockchain hackathon (spoiler: he was on the winning team, scoring $50k. Details next week), leading to his participation in several panels in what he describes as the best conference he's been to in the space. 
We further discuss Ethereum's Proof of Stake protocol that Greg's leading the design of using Synereo technology, talk about dev work done over the past week, and the whole gang gives their take on the best growth vectors for Synereo. (Dor thinks it's building a giant out of midgets.)
<BR>

Another important announcement is about Synereo's newest team member, Jed Walls. Jed has been on [Synereo's advisory board](https://discuss.synereo.com/t/synereo-about-us/52468/2?u=dor) for a year now, advising the team in every step of the way, and has now relocated to Silicon Valley to ramp up his involvement. Jed will be directing a coordinated marketing effort and handling public relations as well as developing the Synereo brand and coordinating our growing community. Welcome, Jed!
![LivelyGig UML](http://imgur.com/8cFBAum)


## Contents in Brief

### [Timeline of Hangout](https://www.youtube.com/watch?v=JH4GLfccKY8) <BR>
[Greg reports from Sydney, Australia](https://youtu.be/JH4GLfccKY8?t=187) <BR>
[LivelyGig Update](https://youtu.be/JH4GLfccKY8?t=900) <BR>
[Introducing Jed](https://youtu.be/JH4GLfccKY8?t=1159) <BR>
[Jed Describes Marketing and Community Plans](https://youtu.be/JH4GLfccKY8?t=1374) <BR>
[What Are The Best Growth Vectors For Synereo?](https://youtu.be/JH4GLfccKY8?t=2015) <BR>
[Further Discussion of Decentralized Reputation Systems](https://youtu.be/JH4GLfccKY8?t=3029) <BR>
[Dor Wants To Map Communities, Calls For Help](https://youtu.be/JH4GLfccKY8?t=3225) <BR>
[Jed Discusses Our Roadmap for Marketing and Community Efforts, Calls for Help ](https://youtu.be/JH4GLfccKY8?t=3351) <BR>


## Detailed Notes

### [Greg reports from Sydney, Australia](https://youtu.be/JH4GLfccKY8?t=187) <BR>

Greg is in Australia participating in a Hackathon on blockchain applications. Interesting projects include one that [Vlad Zamfir](https://twitter.com/VladZamfir) is working on to implement access control mechanisms on the blockchain.

Another project aims to create a decentralized market for decentralized power distribution. The idea is that individuals or groups can meter, store, and exchange power within a local group, as well as sell it to the regional power grid.

# TCS, India
Greg spoke with TCS, a large software services supplier (TATA) in India who is looking to implement blockchain services for their merchants.

# Regulation on high level
Greg discussed smart contracts and securities with a panel of Australian regulators and legal experts. He explained some differences between contracts in the legal world, vs smart contracts capable of autonomous agency.

# Concerns about Proof of Stake
Greg has been working with Ethereum on Casper, a 'proof of stake' protocol that could replace the expensive 'proof of work' system for verifying transactions on the blockchain. He is concerned that Casper might enable an attack against a transaction by pricing it out of the scheduling queue.

# GLoSEval
Greg is working to patch a known bug in glosEval. Justin's importer has been pounding at it, causing server bounces and service bounces.

# Eric & Dina help Noy with UI-design
Greg met with Eric & Dina. Dor confirms that the couple will be helping Noy design Synereo's new user interface.


### [LivelyGig Update](https://youtu.be/JH4GLfccKY8?t=900) <BR>
![LivelyGig UML](http://i.imgur.com/u5mC06l.png)
![LivelyGig UML2](http://i.imgur.com/WFB0SY4.png)


This is a UML class diagram. Not all the details are added. It’s a [high level overview](high level overview).

Green denotes classes that work on the Back-End of Synereo/SpecialK.
The ‘Alias’ connection is a ‘self’ connection, in that it connects a user with him/herself and enables users to maintain more than one identity. Labels live on connections and can be nested. 

Posts do not have searchable ID’s! They are blobs which can only be located by referencing labels that are associated with them. 


### [Introducing Jed](https://youtu.be/JH4GLfccKY8?t=1159) <BR>

The content of posts on LivelyGig and Synereo are secured in such a way as to expose only the minimal amount of metadata necessary for the system to function. The content of Posts are not even visible to the server running the application.

Greg explains that the labeling structure in its relationship to the blob is kind of homomorphic encryption. The structural labeling mechanism where labels have a internal structure. So unlike tags and tagging you can have nested labels and collections of labels inside labels and so on. And there will be some mapping between that and the structure that the data is accessed be in a label. That mapping is entirely maintained by the application semantics. So the backend has no idea about what the relationship is between the label structure and the structure of the data that is retrieved by the label. So this gives us a layers security while at the same time it gives a mean to do search. The benefits of semantic access are that we can maintain our promise never to have access to user data. That’s part of the rational of this architecture.


### [Jed Describes Marketing and Community Plans](https://youtu.be/JH4GLfccKY8?t=1374) <BR>

![LivelyGig Posts](http://i.imgur.com/fa1f0Yv.png)

Content of posts is hidden, however some labeling and metadata must necessarily be exposed in order for the system to operate. Synereo and LivelyGig share a common “MessagePost” that encapsulates these labels and metadata.

Ed identifies some sub-types of Posts such as: Project, contest, offering, buyer profile, seller profile, moderator profile, and contract. Some of these sub-types contain meta-data which is publicly visible, ie profile. Contracts are a special sub-type that contains meta-data viewable only to the parties involved.

### [What Are The Best Growth Vectors For Synereo?](https://youtu.be/JH4GLfccKY8?t=2015) <BR>
![Synereo Stack Diagram](http://i.imgur.com/juNN4vG.png)

The “Agent User Model” layer is referenced as “UserAgent” in the preceding LivelyGig Web UI Class diagram. This layer is common to Apps on this platform that share the same Introduction Protocol, Labels, and Aliases.

### [Further Discussion of Decentralized Reputation Systems](https://youtu.be/JH4GLfccKY8?t=3029) <BR>

Public information (Project, contest, offering, buyer profile, seller profile, moderator profile) are rebroadcast over the network, however contracts are not. There is likely, however, to be some mechanism by which LivelyGig derives a commission for facilitating the contract.

### [Dor Wants To Map Communities, Calls For Help](https://youtu.be/JH4GLfccKY8?t=3225) <BR>
![Connections and Storage on Synereo](http://i.imgur.com/SkjVm8g.png)


Storage and communications are expressed as channels / connections . Channels encapsulate layers of nested labels (meta-data) and private posts. Everyone is an “Agent” that has their own “self” channel that stores private communications. Every communication between Agents occurs over its own unique channel.

### [Jed Discusses Our Roadmap for Marketing and Community Efforts, Calls for Help ](https://youtu.be/JH4GLfccKY8?t=3351) <BR>
![Synereo Compliation](http://i.imgur.com/YYjldZT.png)


Greg compiled the latest Synereo node from Scala and demonstrated a visitor connecting to Synereo through a web front end. The UI is under active development. Greg is awaiting graphic assets from Noy so that he can re-skin to a more beautiful design.

![LivelyGig UI](http://i.imgur.com/ro7E2DP.png)


That's all for this week!
