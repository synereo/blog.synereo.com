---
layout: post
title: 'Extending the Synereo network'
---
The entire class of social services we all use today are dubbed *networks* while they are nothing more than behemoth *applications*. Sure, they give you APIs to build your app on - to their immediate monetary benefit, of course - but the *networks* themselves are walled gardens which you are not allowed to play in. Synereo *truly is* a social **network**, and here's why.

In our previous post [we introduced some of the key concepts Synereo is built on](/blog/2015/02/09/hello-world.html). Today, we'd like to broaden the discussion on a issue that is very important for the future growth of the network - extensibility. Synereo is built from the ground up to not only deliver a complete user experience, but not less importantly, to enable an entire ecosystem around the attention economy model we have implemented. First, lets recap what the Synereo tech stack looks like:

![Synereo Tech Stack](/img/uploads/stack.png)

For the sake of this discussion, we'll ignore the two bottom layers (they are both very interesting, and will definitely be covered in future posts) and start the discussion from the actual deliverables. On the top layer, we have Synereo, the social network *par excellence*. When most users think of Synereo, they think of the actual application, where they can write posts, listen to their favorite artists latest hits and catch up with their friends' photos from their vacation in Costa Rica. Further down the stack we have the Synereo attention economy model API and the Synereo network model API, which not only provide the core functionality for the network, but are also the main entry points for external applications interfacing with the Synereo network.

Let's first take a look at what each layer provides us.

## Network Model API

The Synereo Network Model API deals with the higher level functions that interact with the Synereo network. Some of these APIs are similar to what you would expect from an API to a modern social application: register applications that can act on the user's behalf, post and receive content programatically, and assist in community management tasks. The Network Model API also exposes graph data and meta-data, so applications can build upon and extend various actions between different nodes.

## Attention Economy Model API

Synereo's Attention Economy Model provides APIs that are on a slightly lower-level, and more abstract, but provide tremendous flexibility for implementing radical new protocols that can enable new ways of social organizing. Using the Economy Model API, developers can take advantage of the core Synereo concepts: AMPs, Reo and Current. The core concept in use here is the *Ceptron*, which can be though of as a unit of information coupled with possible actions. Ceptrons are the core building block which can be extended to imeplement anything from social protocols to smart contracts.

## Use Cases

Finally, lets see some actual examples that showcase some of the possibilites.

### Marketplaces

By implementing simple protocols on top of the Synereo APIs, a developer can create a rather sophisticated marketplace, where goods or services can be traded by using AMPs as the currency of exchange, not just as organic compensation for high-quality content, but also as a currency for trading at fixed prices.

### Web Applications

Naturally, any standard application that builds on the Synereo infrastructure can be integrated, just as with any other social application service: build bots that listen, act and respond to network actions and post content on the user's behalf. All these options can be implemented not only by interfacing with Synereo's low level networking protocols, but also via standard RESTful HTTP calls that are processed by middleware adapters installed on the nodes themselves.

### Content Policies

Consider a situation in which a doctor recently back from an aid mission to Sierra Leone leaves a hospital in a densely populated city in the US after having been erroneously cleared as ebola-free. The hospital discovers the mix up, and the doctor is at large, potentially spreading a deadly disease around the city. In such a situation the CDC may wish to ensure that healthcare providers and city officials are notified before any member of the press is notified. How would such a policy be expressed and enforced in a distributed communication network like Synereo? In our upcoming whitepaper, we show a specification of (the relevant communications of) such a system, together with a specification of the properties we want the system to hold, such as, eventually everybody gets the update, but the healthcare providers get it first.

These are all just some use cases we quickly came up with. We're really just scratching the surface. How can *you* extend Synereo?
