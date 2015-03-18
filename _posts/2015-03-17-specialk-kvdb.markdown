---
layout: post
status: publish
published: true
title: SpecialK/KVDB - A Pattern Language for the Web
date: '2015-03-17 22:37:02 +0200'
---

After 26 years in the industry, I can still say what excites me about technology. For me, it has always been about the potential to bring together precision, beauty, and utility into a single functioning whole. For example, take the code that organizes entire networks of computers and the services running on those computers into an application that serves real people. That code needs to be just so: neither too rigid to fail to accommodate a certain misuse, nor too informal to allow any behavior whatsoever. In order for code like that to last long enough for people to be able to realize any benefit from it, it has to have a good enough shape that people can recognize when it is out of shape and also when that shape needs to change to continue to serve people. 

In practical terms, the code for real Internet-scale applications—at least ones that help people do something they actually want or need to do—not only has a form that supports its function, it has a lifespan and a lifecycle. People who maintain that code throughout its lifecycles and through its whole lifespan have to be able to relate said code’s function to its form. The relationship of form and function in a codebase for an Internet-scale application—and, again, i’m talking about the ones that manage to stay in the game long enough for people to get something out of them—is all about a kind of wabi-sabi, rough-and-ready, just-so quality. That’s what I mean by bringing precision, beauty, and utility together into a single whole.

![image alt text](/img/uploads/magnitude.jpg){: style="float: left; margin-right: 15px;"}

## Pop, pop! Or, the *Magnitude* of making precision, beauty, and utility evident in real code 

As I built SpecialK/KVDB, that was the quality I had in mind. What could help people who build these kinds of large scale systems see more clearly when that quality was present in their code? What could enable more than just a handful of people to be able to get to that place? What could help the majority of developers get to the point where they could see for themselves the relationship of form and function; and not just of their code, but of the entire end-to-end system they were helping to build? What could make it so that the vision wasn’t obscured by the details, but rather the details were seen clearly as necessary elaborations of the vision?

To build something like that, I knew it had to be something a little different from an API, something a little different from a programming model, something a little different from a formalism. There are plenty of each of those. Being a big fan of the architect Christopher Alexander, I realized I was looking for something akin to what he calls a *pattern language*. I was looking for something like the set of basic motifs, patterns, and forms that people in cultures around the world use to build houses that feel like homes: the kinds of patterns that make a dwelling in Brazil or South Africa or the south of France immediately recognizable as specific to that region yet also recognizable as ‘home’ to just about anyone. 

Moreover, I knew I was looking for a set of design patterns I could embed in a modern programming language, while at the same time making them available via all the modern protocols, from HTTP to AMQP. I also knew it had to be possible to layer known design patterns—like CRUD, for example—over top of these patterns in a way that people could see how the tried and true related to the new. 

Finally, I knew that this was an incredibly tall order, much too tall for someone like me to fill. I was going to have to stand on the shoulders of people already standing on the shoulders of giants if I was going to have a hope of fulfilling it. The trick, it seemed to me, was to seek out the people at the forefront of concurrency theory—people like Robin Milner, and Tony Hoare, and Samson Abramksy, and Kohei Honda, and Luca Cardelli, and Andy Gordon—and the people at the forefront of modern language design—people like Simon Peyton-Jones, and Oleg Kiselyov, Xavier Leroy and Martin Odersky, and Erik Meijer and Anders Hejlsberg—and take their best insights.  Take what the concurrency theorists were sharing about how autonomous communicating processes can be organized via a few simple design patterns, and fit those ideas together with what the programming language people were saying about the utility of monads for adding design patterns into a core language. And in particular, pay attention to the patterns, like LINQ, that related data storage and access to messaging and complex event processing at web-scale.

## A pattern language for the Web

And, to make a long story short, that’s what SpecialK/KVDB is. Yes, it's a decentralized, distributed storage mechanism that's been in commercial use for over two years, but really, it's a pattern language for building decentralized, distributed applications. It’s kind of funny, because it’s much easier to write down the patterns than to say why they’re important! That page and half before this paragraph is just a preamble to get a sense of why the patterns you’re about to see should be of interest to you, the web developer. So, without further ado, here they are. This is how application programmers query for:

    for ( e <- chan?( cnxn )( pattern ) where cond( e ) ) {
        handle( e )
    }

and publish data:

    chan!( cnxn )( pattern, data )

This single pattern covers all the models, from pub/sub to traditional transacted store to no-sql to distributed transactions.

Here’s a picture of how this basic pattern maps onto storage and messaging.

![image alt text](/img/uploads/patternlanguage4web.jpg)

One entry into the pattern begins with an intuitive map between this pattern and URLs. The `chan?( cnxn )` part of a query or publication can be likened to the `protocol://host:port` part of a URL. The pattern part can be likened to the `path?query-string` part of a URL. A full treatment of the details reveals that this shape is a generalization of the URL notion. Perhaps the biggest generalization is that pattern can cover not just a single resource, but a whole range of resources because it identifies not just a single location in the network of resources, but a whole range of locations that match the pattern. That said, I believe the key insight underlying this design pattern, the one that gives it potency and reach, is the duality of data and query.

## Duality between data and query

In a simplified view of the data/query duality, when a query seeks resources at a pattern and it finds nothing, then a *continuation* is stored at the pattern, instead. The continuation represents what the program or process querying for the resource will do after it gets a resource, were it to have gotten one. We have access to this because the programmer gave it to us explicitly; it’s what’s between the curly braces of the for-comprehension in a query expression:

    for( e <- chan?( cnxn )( pattern ) where cond( e ) ) {
        handle( e )
    }

The system guarantees that the expression `handle( e )` will only ever wake up and start running if a resource satisfying `cond( e )` shows up at 

    chan?( cnxn )( pattern )

Thus, when data is published via `chan!( cnxn )( pattern, data )`, the first things to do are check to see if there are any continuations waiting there and whether data satisfies the necessary conditions to hand them to the any of the awaiting continuations. If there are, then each such continuation is applied to the data.

![image alt text](/img/uploads/traddbops.jpg)

The principal reason to organize things this way is because all the of modern programming patterns, from ordinary transacted storage to no-sql to messaging to distributed transactions, can be expressed in terms of whether data and continuation persist after they meet at a pattern. The read/write of an ordinary store persists the data but removes the continuation. In a publish/subscribe mechanism, the continuation is persisted and the data is not. What’s really cool is how this maps to distributed transactions, but it’s outside of the scope of this paper to describe it.

![image alt text](/img/uploads/tradmsgops.jpg)

![image alt text](/img/uploads/itemlevellockops.jpg)

## The features, advantages, and benefits of web-scale pattern language

One of my key goals was to be able to help more programmers see their vision of the end-to-end system reflected back at them through their code. A real test of that would be to take programmers who are not familiar with things like π-calculus or monads, the mathematical underpinnings of the SpecialK pattern language, and give them this pattern language and see whether and how well they could build distributed web scale applications. 

We did just that with the folks at Protegra. We were able to take programmers predominantly familiar with Java web stack technologies and have them programming decentralized, distributed applications in weeks. You can look at [Protunity](http://www.protunity.com) to see one of the services built this way.

Another key feature is that many of the advanced capabilities coming from the source technologies apply directly to this pattern language. Among these technologies, perhaps the most exciting are the behavioral types. Behavioral types represent a dramatic extension of the notion of typing; ordinary typing principally ensures things like that a function receives data the shape of which matches the shape it was expecting. Behavioral typing ensures properties of the *behaviors* of programs and processes. For example, session types—a particular kind of behavioral type discipline—can be used to guarantee that concurrent programs don’t deadlock. Think about that for a minute: before code passes successfully through the type-checker, it’s guaranteed to be free of deadlocks. That dramatically simplifies one of the thorniest issues in writing distributed systems, and it’s done automatically.

Behavioral types can also express and ensure properties of information flow. For example, they can ensure that information isn’t leaked to unauthorized parties. This means there is a compile-time technology to manage security on the web that becomes available when developers use the pattern language proposed here. Behavioral types are the secret sauce inside Synereo's [social contracts and social graces](http://blog.synereo.com/2015/03/06/social-contracts-pt-ii/).

Again, reflect for a moment: today developers write in scores of idioms over dozens of technologies. The verbosity of such code serves predominantly to obfuscate the design, making it expensive to track the relationship of design to implementation. In this pattern language, the code becomes an ally to support programmers’ intuitions about the system in the small and in the large. At the same time a whole new kind of compiler and type-checking technology becomes available to help manage the complexity of writing distributed applications. This should be more than enough to justify the development and adoption of such a pattern language—but in point of fact, it’s actually just the beginning of what’s possible with this approach to programming the Web.

## The invitation

We’d like to tell you more about these possibilities, and that’s why we’re inviting you to engage with us. We believe that it’s time for a dialogue about what you find exciting about technology and the Web. We believe that you already know when something has that quality of being just so, of being a functioning whole that serves a real need; together, we can bring that knowledge into direct applications.

# Bibliography

Rather than just providing in place links, we thought it might be a nice old school gesture to provide an actual bibliography. If you haven't had the pleasure of reading these texts, you're in luck! Some of these books and papers just might change the way you engage your life beyond the Internet.

Alexander, Christopher (1977). *A Pattern Language: Towns, Buildings, Construction*. Oxford University Press, USA. p. 1216. [ISBN](http://en.wikipedia.org/wiki/International_Standard_Book_Number) [0-19-501919-9](http://en.wikipedia.org/wiki/Special:BookSources/0-19-501919-9).

Luís Caires: Logical Semantics of Types for Concurrency. [CALCO 2007](http://dblp.uni-trier.de/db/conf/calco/calco2007.html#Caires07): 16-35

Luís Caires: Behavioral and Spatial Observations in a Logic for the pi-Calculus. [FoSSaCS 2004](http://dblp.uni-trier.de/db/conf/fossacs/fossacs2004.html#Caires04): 72-89

[Martín Abadi](http://dblp.uni-trier.de/pers/hd/a/Abadi:Mart=iacute=n.html), [Ricardo Corin](http://dblp.uni-trier.de/pers/hd/c/Corin:Ricardo.html), Cédric Fournet: Computational Secrecy by Typing for the Pi Calculus. [APLAS 2006](http://dblp.uni-trier.de/db/conf/aplas/aplas2006.html#AbadiCF06): 253-269

[Martín Abadi](http://dblp.uni-trier.de/pers/hd/a/Abadi:Mart=iacute=n.html), [Bruno Blanchet](http://dblp.uni-trier.de/pers/hd/b/Blanchet:Bruno.html), Cédric Fournet: Just Fast Keying in the Pi Calculus. [ESOP 2004](http://dblp.uni-trier.de/db/conf/esop/esop2004.html#AbadiBF04): 340-354

Andrew D. Gordon: Provable Implementations of Security Protocols. [LICS 2006](http://dblp.uni-trier.de/db/conf/lics/lics2006.html#Gordon06): 345-346

Andrew D. Gordon: Types for Cryptographic Protocols. [CONCUR 2002](http://dblp.uni-trier.de/db/conf/concur/concur2002.html#Gordon02): 99-100

Robin Milner: Functions as Processes. [Mathematical Structures in Computer Science 2](http://dblp.uni-trier.de/db/journals/mscs/mscs2.html#Milner92)(2): 119-141 (1992)

Robin Milner: The Polyadic Pi-calculus (Abstract). [CONCUR 1992](http://dblp.uni-trier.de/db/conf/concur/concur1992.html#Milner92): 1

Philip Wadler: Propositions as sessions. [ICFP 2012](http://dblp.uni-trier.de/db/conf/icfp/icfp2012.html#Wadler12): 273-286

[James Cheney](http://dblp.uni-trier.de/pers/hd/c/Cheney:James.html), [Sam Lindley](http://dblp.uni-trier.de/pers/hd/l/Lindley:Sam.html), Philip Wadler: A practical theory of language-integrated query. [ICFP 2013](http://dblp.uni-trier.de/db/conf/icfp/icfp2013.html#CheneyLW13): 403-416

[Tom Schrijvers](http://dblp.uni-trier.de/pers/hd/s/Schrijvers:Tom.html), [Peter J. Stuckey](http://dblp.uni-trier.de/pers/hd/s/Stuckey:Peter_J=.html), Philip Wadler: Monadic constraint programming. [J. Funct. Program. 19](http://dblp.uni-trier.de/db/journals/jfp/jfp19.html#SchrijversSW09)(6): 663-697 (2009)

Philip Wadler: Monads and Composable Continuations. [Lisp and Symbolic Computation 7](http://dblp.uni-trier.de/db/journals/lisp/lisp7.html#Wadler94)(1): 39-56 (1994)

Philip Wadler: Comprehending Monads. [Mathematical Structures in Computer Science 2](http://dblp.uni-trier.de/db/journals/mscs/mscs2.html#Wadler92)(4): 461-493 (1992)

