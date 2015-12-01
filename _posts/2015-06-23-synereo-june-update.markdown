---
layout: post
status: publish
published: true
title: Synereo June Update
date: '2015-06-23 08:00:00 +0200'
---

Dear Synereo supporters,

The time has come for another update on what the team has been working on. 

**Synereo AMP Tokens Doubled**

As mentioned in [our previous update](http://blog.synereo.com/2015/05/10/amp-distribution-complete/), we were going to double all the coins paid out to crowdsale contributors as well as those in other AMP wallets. This process is now complete, and you can see the results in the public wallets:

* [AMP Property Page](http://omnichest.info/lookupsp.aspx?sp=39)

* [Crowdsale Wallet](http://omnichest.info/lookupadd.aspx?address=3Q7T1ES6atTpeSid3w17HS3eEsHbhQC9jf)

* [User Reward Wallet](http://omnichest.info/lookupadd.aspx?address=38X3p54WftkmiQmywwzvQzv5ZmbpwWndLL)

* [Content Creator Wallet](http://omnichest.info/lookupadd.aspx?address=3594LvBdb7epiJQ3domUH52p3UFMJK7AoW)

* [Founder Reward Wallet](http://omnichest.info/lookupadd.aspx?address=3AKjXkuBEyaXfuXVfdf1VUBAzGPR49NifM)

* [Bounty Wallet](http://omnichest.info/lookupadd.aspx?address=3No5y1WuEh4LSEFNngyPdEmyMUqS8rBCWb)

* [Future Funding Wallet](http://omnichest.info/lookupadd.aspx?address=34MWvp1xfxaaqXENxWW45uqDfuNY9f8hr2)

**Unsold Crowdsale AMPs Burned**

AMPs that were unsold during the crowdsale have now been burned (revoked). You can see the revoked transaction for 319,600,000 coins [here](http://omnichest.info/lookuptx.aspx?txid=1076c1667d349d39f6ac8dcbbf2665b8c27ab089cd427c107130241aa8d2b549). 

**Bounties Payouts Complete**

We have issued 8 bounty payouts for our Twitter and MVP contest winners. We are happy to announce the payouts have now been completed and want to thank again the participants for showing their support during the crowdsale! You can see the details in the [Synereo Community Rewards](https://docs.google.com/spreadsheets/d/184coQnQX7YUfbSxTaoTNphqkwp9XhJo9EanwWC_OIeg/edit#gid=0) sheet. Going forward we will have some of the funds transferred to a non multisig wallet to be able to make bounty payments swiftly. 

**Dev Updates**

On the backend we are busy updating some dependencies. To do this in a sane fashion we have taken apart the tech stack at the comms and storage layers to be able to test them independently. The comms layer update is mostly complete. There’s one dependency we want to remove (a deprecated scala actors usage on the send path), but we’ll do that after completing all the tests with the new version of RabbitMQ. With luck this will be merged into master on the Synereo repo this week and we’ll begin on the storage update. For those who love the details, we also ported Synereo’s build from maven to sbt. We also did some exploratory work to see how much work it would be to port to scala 2.11. 

**Synereo Community Hangout Wednesdays**

Our Wednesday Community Hangouts have been proceeding in full force. Every week, we’ll be live, talking about our plans and progress. If you want to stay up to date and have the opportunity to speak to the team directly, you are invited to join. We will promote the Hangouts on our [Google+](http://google.com/+Synereo), [Twitter](https://twitter.com/Synereo), and [Facebook](https://facebook.com/synereo) each week.

Five of the last six weeks have been devoted to discussion of the front end design and development work. We interrupted the front end discussion series (entitled Reactive Media) to give an update on the backend development work. The Reactive Media series will be posted as blog entries, but if you are feeling impatient, feel free to check out the slide decks that were used in the community hangouts.

* [Reactive Media Pt I - applying the core abstractions of reactive programming to social media](https://drive.google.com/file/d/0B5I9qM5f_1cfdHVqT3Z1dTJNaVU/view?usp=sharing)

* [Reactive Media Pt II - mapping those abstractions to basic elements of user experience](https://drive.google.com/file/d/0B5I9qM5f_1cfd1VuYWoyWlJBaE0/view?usp=sharing)

* [Reactive Media Pt III - the elements of engagement and the building blocks of the attention economy](https://drive.google.com/file/d/0B5I9qM5f_1cfUGw3LTVjQkpsVTQ/view?usp=sharing)

* [Reactive Media Pt IV - simplifying the experience](https://drive.google.com/file/d/0B5I9qM5f_1cfQWFrUFVHbEFNUWc/view?usp=sharing)

* [Reactive Media Pt V - mapping this design to actual form factors](https://drive.google.com/file/d/0B5I9qM5f_1cfc1BWUnVia0hRSHM/view?usp=sharing)

**Synereo Community Slack**

We would also like to remind our supporters that we have a Community Slack for real time discussion with the team and other community members. Slack is open to everyone; simply submit your email address to get an invite here: [https://slack.synereo.com](https://slack.synereo.com). 

<br>

The Synereo Team

*Be Part of the Solution*

