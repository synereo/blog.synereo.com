---
layout: post
status: publish
published: true
title: Scribe Notes For Synereo Weekly Update
date: '2015-12-07 08:00:00 +0200'
---

## Scribe Role Update
[Last week](http://blog.synereo.com/2015/12/02/new-bounty/), we announced the new Scribe role and the bounty for undertaking it. In an awesome show of solidarity, our community split the task between each other and shared the take with the team. This is just the kind of thing we’ve come to appreciate from the Synereo community: it is truly a place where people are working together to realize a vision. 
<BR>

Because they worked together, the level of detail and precision in the meeting notes created by our scribes is amazing. We never expected to have this level of detail and we are happy to report that we will be delivering such quality in our weekly meeting notes. We can’t thank them enough. 
<BR>

This week we had a great update with the crew from LivelyGig: where it is at, how its UI functions, structure, and how they have successfully addressed some of the biggest technical challenges in their field. We discussed homomorphic obfuscation, which is a kind of encryption that happens in the Synereo system.
<BR>

We also ran through a live demo of Synereo. Greg created a Synereo node and demonstrated how Synereo operates. Noy, our designer, is busily working with Dor on graphics so we can roll out our visual design. Dor gave updates about his efforts to secure funding, negotiating with investors in order to find financial partners who truly care about changing the world for the better and who are aligned with our values. As well, Synereo is looking to go into an equity crowdsale using the Bank To The Future platform once the first public app is released. 

We also discussed streaming media over Synereo, how to connect to the stack through a frontend, and more. 
See the video index and the Scribe notes below.
<BR>

## Contents in Brief

### [Timeline of Hangout](https://www.youtube.com/watch?v=mUF5hWVdxRQ) <BR>
[02:34 - LivelyGig Update](https://youtu.be/mUF5hWVdxRQ?t=234) <BR>
[04:80 - LivelyGig Web UI Classes](https://youtu.be/mUF5hWVdxRQ?t=480) <BR>
[08:55 - Homomorphic obfuscation of posts](https://youtu.be/mUF5hWVdxRQ?t=855) <BR>
[12:40 - How posts are structured in LivelyGig](https://youtu.be/mUF5hWVdxRQ?t=1240) <BR>
[17:50 - Stack diagram of Synereo](https://youtu.be/mUF5hWVdxRQ?t=1750) <BR>
[19:71 - Visibility and broadcasting of Gigs, Profiles, and Contracts](https://youtu.be/mUF5hWVdxRQ?t=1971) <BR>
[22:54 - Connections and Storage on Synereo (abstract), security model](https://youtu.be/mUF5hWVdxRQ?t=2254) <BR>
[26:29 - Synereo live demo - compilation and execution](https://youtu.be/mUF5hWVdxRQ?t=2629) <BR>
[29:93 - Dor's updates - banktothefuture.com](https://www.youtu.be/mUF5hWVdxRQ?t=2993) <BR>
[32:28 - Jim's updates and observations](https://youtu.be/mUF5hWVdxRQ?t=3228) <BR>
[40:06 - Streaming media content over Synereo](https://youtu.be/mUF5hWVdxRQ?t=4006) <BR>
[43:35 - bitnation.co & Self Determination](https://youtu.be/mUF5hWVdxRQ?t=4335) <BR>

## Detailed Notes

### [02:34 - LivelyGig Update](https://youtu.be/mUF5hWVdxRQ?t=234) <BR>

UI trend and rational makes a lot of sense: be clear about the personas of the prototypical users that are on the site and understand quickly by either login info or by them specifying what their goals are. As a freelancer your primary goal is to find work and as a client your primary goal is to find a freelancer for a particular task in a project. That changes the UI accordingly. We will address that UI later, but we’re still building up the technology side of LivelyGig UI. <BR>

We had several conversations: <BR>

* freelance organisation Domino, which is a community that supports freelancers. 

* And also with Suzie Nguyen. Maybe Greg is going to visit her in Sydney this week.

* Engzig they working on a freelance market that will match up engineers in petroleum industry. Fascinating story about engineers that are put on 2 month jobs without the right credentials. So their referees are very important as well as credentials from certifying organisations

* Onboarding of users onto LivelyGig and how to minimize the friction. Will we require basic login for doing searches or not? And at what point do we take that information.

* And we’re working on fundraising activities.

### [04:80 - LivelyGig Web UI Classes](https://youtu.be/mUF5hWVdxRQ?t=480) <BR>
![LivelyGig UML](http://i.imgur.com/u5mC06l.png)
![LivelyGig UML2](http://i.imgur.com/WFB0SY4.png)


This is a UML class diagram. Not all the details are added. It’s a [high level overview](high level overview).

Green denotes classes that work on the Back-End of Synereo/SpecialK.
The ‘Alias’ connection is a ‘self’ connection, in that it connects a user with him/herself and enables users to maintain more than one identity. Labels live on connections and can be nested. 

Posts do not have searchable ID’s! They are blobs which can only be located by referencing labels that are associated with them. 


### [08:55 - Homomorphic obfuscation of posts](https://youtu.be/mUF5hWVdxRQ?t=855) <BR>

The content of posts on LivelyGig and Synereo are secured in such a way as to expose only the minimal amount of metadata necessary for the system to function. The content of Posts are not even visible to the server running the application.

Greg explains that the labeling structure in its relationship to the blob is kind of homomorphic encryption. The structural labeling mechanism where labels have a internal structure. So unlike tags and tagging you can have nested labels and collections of labels inside labels and so on. And there will be some mapping between that and the structure that the data is accessed be in a label. That mapping is entirely maintained by the application semantics. So the backend has no idea about what the relationship is between the label structure and the structure of the data that is retrieved by the label. So this gives us a layers security while at the same time it gives a mean to do search. The benefits of semantic access are that we can maintain our promise never to have access to user data. That’s part of the rational of this architecture.


### [12:40 - How posts are structured in LivelyGig](https://youtu.be/mUF5hWVdxRQ?t=1240) <BR>
![LivelyGig Posts](http://i.imgur.com/fa1f0Yv.png)

Content of posts is hidden, however some labeling and metadata must necessarily be exposed in order for the system to operate. Synereo and LivelyGig share a common “MessagePost” that encapsulates these labels and metadata.

Ed identifies some sub-types of Posts such as: Project, contest, offering, buyer profile, seller profile, moderator profile, and contract. Some of these sub-types contain meta-data which is publicly visible, ie profile. Contracts are a special sub-type that contains meta-data viewable only to the parties involved.

### [17:50 - Stack diagram of Synereo](https://youtu.be/mUF5hWVdxRQ?t=1750) <BR>
![Synereo Stack Diagram](http://i.imgur.com/juNN4vG.png)

The “Agent User Model” layer is referenced as “UserAgent” in the preceding LivelyGig Web UI Class diagram. This layer is common to Apps on this platform that share the same Introduction Protocol, Labels, and Aliases.

### [19:71 - Visibility and broadcasting of Gigs, Profiles, and Contracts](https://youtu.be/mUF5hWVdxRQ?t=1971) <BR>

Public information (Project, contest, offering, buyer profile, seller profile, moderator profile) are rebroadcast over the network, however contracts are not. There is likely, however, to be some mechanism by which LivelyGig derives a commission for facilitating the contract.

### [22:54 - Connections and Storage on Synereo (abstract), security model](https://youtu.be/mUF5hWVdxRQ?t=2254) <BR>
![Connections and Storage on Synereo](http://i.imgur.com/SkjVm8g.png)


Storage and communications are expressed as channels / connections . Channels encapsulate layers of nested labels (meta-data) and private posts. Everyone is an “Agent” that has their own “self” channel that stores private communications. Every communication between Agents occurs over its own unique channel.

### [26:29 - Synereo live demo - compilation and execution](https://youtu.be/mUF5hWVdxRQ?t=2629) <BR>
![Synereo Compliation](http://i.imgur.com/YYjldZT.png)


Greg compiled the latest Synereo node from Scala and demonstrated a visitor connecting to Synereo through a web front end. The UI is under active development. Greg is awaiting graphic assets from Noy so that he can re-skin to a more beautiful design.

![LivelyGig UI](http://i.imgur.com/ro7E2DP.png)

### [29:93 - Dor's updates - Synereo going into an equity crowdsale](https://www.youtu.be/mUF5hWVdxRQ?t=2993) <BR>

Ramping up for Synereo's first public release in a couple of months, Dor is lining up more investors. Synereo will be going into an equity crowdsale using Simon Dixon's platform, [Bank To The Future](https://bnktothefuture.com/).
He will be judging in an [online Ethereum Hackathon](http://hack.ether.camp/judges). Last week, he presented at the annual Israeli Bitcoin convention. You can see his presentation [here](https://www.dropbox.com/s/qtl4dyobandu4qh/Israeli%20Bitcoin%20Conference%20Synereo%20Presentation.pptx?dl=0). 

### [32:28 - Jim's updates and observations](https://youtu.be/mUF5hWVdxRQ?t=3228) <BR>

FreeTrust update. Hopes for an XMPP interface for Synereo. Talk of theoretical and mathematical models. Pi calculus, Calculus of Distinctions, Set Theories, etc

### [40:06 - Streaming media content over Synereo](https://youtu.be/mUF5hWVdxRQ?t=4006) <BR>

Initially, Synereo will not host streaming content itself, but will link content via a look-aside table. Future versions of Synereo will fragment the storage and delivery of streaming media among many servers.

### [43:35 - bitnation.co & Self Determination](https://youtu.be/mUF5hWVdxRQ?t=4335) <BR>

Brief reflection on last week’s hangout with John from http://bitnation.co

That's all for this week!
