---
layout: post
status: publish
published: true
title: On social contracts - Part II
date: '2015-03-06 22:37:02 +0200'
---
In a decentralized, distributed web nobody's in charge. Or rather, everybody's in charge of themselves. How do we get from that place of potential chaos to a self-organizing and civilized web? It's all about the protocol.

**TL;DR: Relax, nobody's in charge.**

**Warning: for people who are used to "smart contracts" this idea may take some getting used to. Patience. There's a method to our madness.**

### Examining a social contract in more detail

Previously, on [Synereo's social contracts](http://blog.synereo.com/2015/02/10/social-contracts-pt/): we asked if there are decentralized, distributed protocols or social contracts that make it possible to uplevel trust and gave an example of the *verification* protocol. In the verification protocol, the roles are the *claimant*, like our character Abed who is pursuing a gig with SoftShop, and making a claim about having a degree in communications; and the *relying party*, like SoftShop, who wants to hire a videographer, and requires them to have a degree in communications; and the *verifier*, a third party, like Greendale Community College, who is mutually trusted just for this one communication to verify to SoftShop just this one claim about Abed's degree.

![image alt text](/img/uploads/verification-protocol-whole.jpg)

Then we asked about a language of social contracts that could map back all the way to running code in a Synereo node. Interestingly, rendering this diagram in such a language clarifies exactly how it is distributed. To see this we need to understand the language in more detail. 

![image alt text](/img/uploads/verification-protocol-claimant.jpg)![image alt text](/img/uploads/verification-protocol-relying-party.jpg)

![image alt text](/img/uploads/verification-protocol-verifier.jpg)

The language of social contracts has just a few primitives. Social contracts bind *agents*. Agents communicate by sending *messages* over *channels*. Messages can include channels as part of the message data they communicate. This last point is very important because taken together with the ability to create *fresh* channels, this is how contracts can span interactions - common place on the Internet today - that involve a dynamically changing communication topology. On eBay, for example, buyer and seller may have never met, or exchanged any communication whatsoever before the buyer wins the auction; but at the close of the auction they become connected, if need be, to work out shipping logistics and other details. 

Out of this handful of primitives comes a model of agent-based synchronization and exchange rich enough to compute with. In fact, it is provably Turing complete. Most folks, i'm guessing, can work out the basics from the examples in the diagrams. For example, we use a for-comprehension for input:

for( e <- chan?( cnxn )( pattern ) ){ … }

This describes waiting on a channel of the form chan( cnxn ) for messages that match pattern. Similarly, 

chan!( cnxn )( message ) 

describes outputting message on that same channel form. For those with a strong inner geek we've included a complete specification of the core social contracts language at the end of this post. 

In our diagrams, each vertical line constitutes (the observable behavior of) an agent. Each horizontal line (arrow) constitutes the exchange of a message with an agent either being the sender or the recipient of a message, depending on whether the tail or the head of the arrow touches the vertical line. With just this information it is possible to walk each line and render it as an agent in the language of social contracts. Each of these agents can run independently and autonomously of the others, and hence can be distributed throughout the Synereo network. Of equally vital importance is that the *whole system of agents* in the verification protocol, the concurrent and distributed collection of claimant, verifier, and relying party agents, working together in concert to verify a claim, *is also an agent*! This is how the language of social contracts, and the Synereo architecture more generally, can address both group dynamics as well as building up contracts recursively in terms of subcontracts and subsubcontracts and … 

![image alt text](/img/uploads/verification-protocol-eye-of-sauron.png)

This latter point is also crucial to **being able to have contracts and contract enforcement without an all-seeing eye in the sky, not even a blockchain.** In particular, claimant, verifier, and relying party could each not only run independently and autonomously, but indeed specify their behavioral policy independently and autonomously, and then the policy of the total system would be built, post facto, as the *parallel composition* of each policy. 

What then allows the participants to determine if the composite contract meets their needs? We're so glad you asked!

### On social graces

If the observable behavior of agents record policy as social contracts, then Synereo's notion of social properties, or *social graces*, if you will, allow interested participants to probe a policy for key requirements and guarantees. Here's a simple example of a social grace. In the protocol above, it is easily demonstrated that the relying party never gets a confirmation message unless the claims match. This can be turned into a logical property that can be checked by any party in possession of the aggregate policy.

In a more advanced version of the protocol, the claimant and relying party negotiate on who is to play the role of the verifier. A simple social grace would require that eventually both parties agree on the verifier if the protocol is to continue to the next phase. Otherwise, all bets are off. A more subtle and discerning grace would insist that the verifier that receives the allowCheck request from the claimant is also the one that receives the confirm request from the relying party. How often do human protocols go awry because there's a question about who really is on the hook to discharge a particular obligation? Just the other day, we got an unexcused absence notice from our child's school even though she was just home sick. Turns out, i thought my wife was calling the school to let them know our daughter was sick and she thought i was, and the call was never made. Ensuring that both parties have selected and are engaged with one and the same verifier is an essential ingredient for this protocol to work. 

As a side note, observe that this requirement doesn't actually necessitate a unique identity for the verifier. The only requirement is that both parties can check they are using the same channel on which to engage the verifier. In everyday terms, a person is not their email address. Emails are not a uniquely identifying tokens, yet both parties can be satisfied if they are using the same email address. Surely, for the purposes of the protocol, if both parties have agreed that the verifier is trustworthy enough to play in the role of verifier, then both parties trust the verifier enough to respond at the channel agreed upon. If both Abed and SoftShop agree to use the same Greendale graduations department email, which both parties can check to their satisfaction, that's enough. They just need to agree on using the same channel of communication, they don't even care if it's the same person reading and responding to the communications, as long as the communications are handled appropriately. And, again, both the simple and more discerning social graces can be rendered as a logical property against which the aggregate protocol may be automatically checked.

Quite apart from the obvious utility of social graces in civil society, Synereo's version of social grace enjoys some remarkable attributes. First of all the checks for graciousness in contracts happen before the contract ever executes! For developers who might be reading this post, it's like a compile time check, such as type checking a program. This feature allows social contracts to be probed at service binding time, before any contract execution takes place. In a world where many service uses social contracts and social graces, this feature in turn, allows for just-in-time provisioning of services, where service providers advertising to provide some piece of a larger contract are pieced together until the whole service requirements are met and all the social graces adhered to. As anyone who works in supply-chain management can attest, [just-in-time provisioning is critical to handling real world situations](http://smallbusiness.chron.com/advantages-justintime-inventory-systems-20997.html).

Further, it is well established that there is a very expressive sublanguage of the language for social contracts for which [the check for social graces is known to terminate](http://citeseerx.ist.psu.edu/viewdoc/summary?doi=10.1.1.3.9964) -- even if the contract itself doesn't terminate. Thus, as long as contracts stay within a certain sublanguage, compliance to which can be checked algorithmically, probing it for conformance to a desired social grace will terminate. By comparison, Ethereum's notion of "gas" as a way of addressing the computing realities of the halting problem seem less refined. Being able to support non-terminating contracts is important if you want to have standing agreements between parties -- contracts that don't terminate except by an action triggered by one or both of the parties, such as an exception clause. Such contracts include everything from a restaurant's standing order for eggs from a local farmer to a data center's standing order for power from the electric company. They form a necessary part of a much wider and richer ecosystem of social contracts.

### Relating social contracts to smart contracts and financial instruments

Back in the day, i was the principal architect for Microsoft's business process orchestration tool, BizTalk Process Orchestration. i used a language very similar to the one for social contracts as the basis for specifying business processes. One day while i was working on this, SimonPeyton-Jones stopped by my office to talk to me about his work on composing contracts. i learned from [his presentation](http://ulf.wiger.net/fp_seminar/Options-Ericsson-Feb08.pdf) that when [when he said contracts he meant financial instruments](http://research.microsoft.com/en-us/um/people/simonpj/papers/financial-contracts/contracts-icfp.pdf). We both wondered what might be the relationship between his contracts and the kind of business processes, or social contracts considered here. 

![image alt text](/img/uploads/spj.png)

What was even more intriguing was that -- as i pointed out to him at the time -- his combinators for building up financial instruments were remarkably similar to [a well known logic called ](http://en.wikipedia.org/wiki/Linear_logic)*[linear logi*c](http://en.wikipedia.org/wiki/Linear_logic). There is [a deep connection between linear logic and the maths underlying social contracts](http://homepages.inf.ed.ac.uk/wadler/papers/propositions-as-sessions/propositions-as-sessions.pdf), presented here. i mention this by way of saying that we at Synereo believe we are only at the beginning of a very exciting journey that connects contracts, the blockchain, and other powerful instruments into a framework for self-organization and self-determination in a decentralized setting, a framework with the power to shape the way we conduct ourselves online and offline for decades to come. 

We're quite excited by the opportunities opened up by all the different approaches to contractual engagement through the Internet. [Ethereum's approach](http://vbuterin.com/ethereum.html) is fascinating! It doesn't seem like they are particularly aware of the work that has gone on before, like Simon's work, or that this work formed a good deal of the thinking and practice at companies like [lexifi.com](http://lexifi.com). Specifically, compositionality, and its relationship to valuation of financial contracts, which in turn relates to being able to trade on contracts, themselves, would seem to be of primary importance. Likewise, being able to guarantee certain constraints on information flow, as we do with social contracts, seems to be of paramount importance to any fiduciary or fiscal agreements and instruments related to exchange on the Internet. Again, i don't see any of this addressed in Ethereum's notion. 

Perhaps more intriguingly, the brinkmanship of the idea of "gas" is thrilling! What happens in a contract if the parties do run out of gas and the stakes are just too high not to at least consider giving it a little more time? How many times would people go around that loop before bailing? Do exit conditions still bind if the parties do decide to give it a little more gas? Once this sort of thing happens, are the parties actually engaged in contract renegotiation in the midst of executing the contract? What happens to contracts that are linked or dependent upon a contract in this state? After 2008 who isn't aware of the web of contract dependencies and how such interlinking can cause wildly unpredictable behavior? Very exciting stuff to be certain, and there'll be more posts about this, you can be sure! But, speaking of the mathematics underlying the language of social contracts...

### On the origins of social contracts and social graces

![image alt text](/img/uploads/robin-milner.png)

For some the language of social contracts and social graces will be familiar. They are a variant of [Robin Milner's π-calculus](http://www.lfcs.inf.ed.ac.uk/reports/91/ECS-LFCS-91-180/) and [Luis Caires' spatial behavioral logic](http://citeseerx.ist.psu.edu/viewdoc/summary?doi=10.1.1.3.9964), respectively. Being able to base our work on the work of a [Turing award winner](http://dl.acm.org/citation.cfm?id=151240) has some benefits. Firstly, the core ideas have been fairly decently QA'd. ;-) Secondly, it means that there is [a wealth of literature that anyone can consult](http://en.wikipedia.org/wiki/Π-calculus). No one need remain in the dark. Thirdly, having such a theory is what allows us to be precise about such things as the sublanguage for which checking logical properties is terminating. Fourthly, not only have these ideas been worked out on paper, there are reference implementations. [Luis Caires' team, for example, have built an open source version of the spatial logic model checker that can be downloaded and played with, ](http://ctp.di.fct.unl.pt/SLMC/)[right now](http://ctp.di.fct.unl.pt/SLMC/). You don't have to wait for Synereo to explore these ideas. You can try them out for yourself. 	

								![image alt text](/img/uploads/luis-caires.png)

### Relating social contracts to code running in a Synereo node

Synereo attracts such amazingly insightful people i'm guessing that you, Dear Reader, are thinking to yourself, "It's all well and good to check that these social contracts observe a modicum of social grace, but how do we know that an implementation conforms to the contract?" Fantastic! We love questions like this! The language bindings for Synereo provide a social contract-based domain specific language (DSL). Literally, when people write Synereo applications using our APIs they are writing social contracts. So, as long as they go through Synereo APIs, they are always ensuring the tightest possible correspondence between their implementation and their code: they are one and the same! Lest this seem too abstract an idea, [here's a link to an implementation of the verification protocol using this API](https://github.com/rlamb/Agent-Service-ATI-IA/tree/cryptoRedo/AgentServices-Store/src/main/scala/com/protegra_ati/agentservices/protocols/verification).

### Specifying the core language for social contracts

##### Syntax

agent **::=** {}							// the empty contract

     **|** for( v <- channel?( cnxn )( pattern ) ) { agent }		// wait on channel for messages 

//	matching pattern then 

//	become agent

     **|** channel!( cnxn ) ( message )				// send message on channel

     **|** agent | agent						// parallel composition of agents

     **|** new channel { agent }					// create a fresh channel for use in 

//	agent

     **|** ( def X( channel ) = agent )( channel )			// recursive definition and initial 

// 	invocation

     **|** X( channel )						// invocation of recursively defined 

//	agent

channel **::=** a, b, c, … 						// entry point to a connected 

//	network of Synereo nodes

cnxn **::=** A, B, C, …						// link between a pair of agents

pattern **::=** value | variable | functor( pattern* )		// patterns are basically prolog 

//	terms

value **::=** boolean | int | float | string | …

variable **::=** X, Y, Z, …

functor **::=** x, y, z, …

##### Structural equivalence

A | B ≡ B | A

A | {} ≡ A

new c { new c { A } } ≡ new c { A }

new c { new d { A } } ≡ new d { new c { A } }

new c { A } | B ≡ new c { A | B }			// provided c doesn't occur free in B

##### Operational semantics

If unifies( pattern, message, subst ) then 

for( v <- c?( pattern ) ) { A } | c!( message ) -> subst( A )

If A -> A' then A | B -> A' | B

If A -> A' then new c { A }  -> new c { A' } 

If A ≡ A', A' -> B', B' ≡ B then A -> B

**Specifying the core language for social graces**

formula ::= formula | formula 

| formula || formula 

| formula => formula 

| formula <=> formula 

| formula and formula 

| formula or formula 

| ( formula ) 

| not formula 

| void 

| true 

| false 

| pattern == pattern

| pattern != pattern

| @ name

| exists name . formula 

| forall name . formula 

| reveal name . formula 

| revealall name . formula 

| hidden name . formula 

| fresh name . formula 

| formula 

| [label]formula 

| minfix CapsId.formula 

| (minfix CapsId (pattern).formula)(pattern) 

| maxfix CapsId.formula 

| (maxfix CapsId (pattern).formula)(pattern) 

| CapsId 

| CapsId(pattern) 

| k 

| inside formula 

| always formula 

| eventually formula 

| Id(pattern,formulalist) 

label ::= tau | name | ? | ! | name? | name! | name?( cnxn )(pattern) | name!( cnxn )(pattern) | *

The relationship of contract to formula is one of satisfaction. ;-) We write contract |= formula just when contract satisfies formula. The semantics of the satisfaction relation is given in Caires' paper, here. A model-checker that implements an algorithmic approach to checking satisfaction between contract and formula can be found [here](http://ctp.di.fct.unl.pt/SLMC/).

