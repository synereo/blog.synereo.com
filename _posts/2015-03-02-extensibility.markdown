---
layout: post
status: publish
published: true
title: Extensibility in Synereo
date: '2015-03-02 12:58:02 -0800'
---

Synereo addresses the needs of multiple communities. In the last couple of posts and community hangouts we talked about serving the needs of performing artists and other members of the creative classes. In this post, we’ll talk about addressing the needs of another creative community: developers! Developers are the lifeblood of the Internet. They make bits sing and dance. Naturally, we want to make it possible for them to work their magic with Synereo. So, this post is all about extensibility, and how developers can shape, mold, and extend Synereo to build apps that we, the founders, didn’t even think about.

![image alt text](/img/uploads/rosie-coder.png){: style="float: left; margin-right: 15px;"}

The entire class of social services we all use today are dubbed *networks,* though they are little more than behemoth *applications*. Sure, they give you APIs to build your app on - to their immediate monetary benefit, of course - but the *networks* themselves are walled gardens which you are not allowed to play in. In that regard, Synereo *truly is* a social **network**. This post will show you why.

In our previous post, [we introduced some of the key concepts Synereo is built on](http://blog.synereo.com/2015/02/09/hello-world/). Today, we'd like to broaden the discussion on an issue that is very important for the future growth of the network: extensibility. Synereo is built from the ground up to not only deliver a complete user experience, but not less importantly, to enable an entire ecosystem around the attention economy model we have implemented. 

First, lets recap what the Synereo tech stack looks like:

![Collective Consciousness](http://stuffo.hswstatic.com/stuffyoushouldknow/wp-content/uploads/sites/14/2013/05/streamconscious_landing.jpg){: style="display: block; margin: 0 auto;"}

For the sake of this discussion, we'll ignore the two bottom layers (they’re both interesting, and will receive the proper treatment in future posts) and start the discussion from the actual deliverables. On the top layer, we have Synereo, the social network *par excellence*. When most users think of Synereo, they think of the actual application, where they can write posts, listen to their favorite artists’ latest hits, and catch up with their friends' photos from their vacation in Costa Rica. Further down the stack, we have the **Synereo attention economy model API** and the **Synereo network model API**. These not only provide the core functionality for the network, but are also the main entry points for external applications interfacing with the Synereo network.

Let's first take a look at what each layer provides us.

## Network Model API

The Synereo Network Model API deals with the higher level functions that govern the Synereo network. Some of these APIs are similar to what you would expect from an API to a modern social application: register applications that can act on the user's behalf, post and receive content programmatically, and assist in community management tasks. The Network Model API also exposes graph data and meta-data - who your friends are, what community you’re most active in - so applications can build upon and extend various actions between different nodes. 

Synereo also exposes access to its semantic layer here. User-generated meta-data elements are first-class entities in Synereo -- meaning they can not only be used to tag content, but can be content and tagged themselves. These elements give users better means to organize and share data with each other. They also provide the basis for rich search, trending and other content analysis features, without compromising privacy. We’re looking forward to seeing what the developer community can do with this!

## Attention Economy Model API

Synereo's Attention Economy Model provides APIs that are on a slightly lower-level, and more abstract, but provide tremendous flexibility for implementing radical new protocols that can enable new ways of social organizing. Using the Economy Model API, developers can take advantage of the core Synereo concepts: AMPs, Reo and Current. 

Want an app that organizes a call for help and takes up a collection for a friend in need, or disaster relief? That’s where these APIs come into play. Want an app that gets the word out and sells tickets for an online benefit concert? Reo is the way to measure community standing and community response. AMPs are the driving force to get content front and center for those who need to see it, while compensating them for their attention. The Attention Economy Model API makes these and other elements programmatically available.

## Technology bindings

![image alt text](/img/uploads/synereo-logo1.png){: style="width: 80px;"}
![image alt text](/img/uploads/scala-logo.png){: style="width: 80px;"}
![image alt text](/img/uploads/java-logo.png){: style="width: 80px;"}
![image alt text](/img/uploads/restful-area.png){: style="width: 80px;"}
![image alt text](/img/uploads/rabbitmq-logo.png){: style="width: 80px;"}
![image alt text](/img/uploads/nodejs-logo.png){: style="width: 80px;"}

Each of these APIs is accessible through a number of options. There are language level bindings for a wide range of popular languages, from Java to Scala, from JRuby to Clojure. Additionally, there are several interprocess communication options, from normal web-based routes, like HTTP, to messaging routes like AMQP providers (e.g. RabbitMQ), and other popular options like ZeroMQ. Similarly, there are bulk data import options for integrating services with high data volume or throughput needs. We’ve even begun work on a node.js bridge. No one should feel uninvited to the party.

## Use Cases

Building on that last point, lets see some examples that showcase some of the possibilities.

### Marketplaces

By implementing simple protocols on top of Synereo’s Attention Model APIs, while respecting connectivity constraints learned through accessing the Network Model APIs, a developer can create a rather sophisticated marketplace. In Attention Model based markets goods or services can be traded by using AMPs as the currency of exchange, not just as organic compensation for high-quality content, but also as a currency for trading at fixed prices. 

### Web Applications

Naturally, any standard application that builds on the Synereo infrastructure can be integrated, just as with any other social application service: build bots that listen, act and respond to network actions and post content on the user's behalf. All these options can be implemented not only by interfacing with Synereo's low level networking protocols, but also via standard RESTful HTTP calls that are processed by middleware adapters installed on the nodes themselves.

### Content Policies

Consider a situation in which a doctor recently back from an aid mission to Sierra Leone leaves a hospital in a densely populated city in the US after having been erroneously cleared as ebola-free. The hospital discovers the mix up, and the doctor is at large, potentially spreading a deadly disease around the city. In such a situation the CDC may wish to ensure that health care providers and city officials are notified before any member of the press is notified. How would such a policy be expressed and enforced in a distributed communication network like Synereo? In our upcoming whitepaper, we show a specification of (the relevant communications of) such a system, together with a specification of the properties we want the system to hold, such as, eventually everybody gets the update, but the health care providers get it first. We’ll talk a lot more about this in the upcoming On Social Contracts Pt II post.

These are all just some use cases we quickly came up with. We're really just scratching the surface. How can *you* extend Synereo?

