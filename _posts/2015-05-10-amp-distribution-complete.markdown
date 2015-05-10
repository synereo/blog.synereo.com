---
layout: post
status: publish
published: true
title: AMP Distribution Complete
date: '2015-05-10 14:45:00 +0200'
author: Nicola Minichiello
---

Dear Synereo supporters,

The team has been working hard to deliver all AMPs purchased during the crowdsale. And as most of your have noticed by now - AMPs are here! 

We would like to take this opportunity and thank each and every one of our supporters again for believing in Synereo’s vision, team and technology.

* Total USD raised: $126,023

* Total Number of AMPs sold: 22,719,689

* Total Number of AMPs distributed: 45,439,378

* Number of AMPs to destroy: 139,360,622

AMPs are now tradable on [MasterXchange](https://masterxchange.com/market.php?currency=mscamp). We’re working to list AMPs on other exchange as well.

If you access your wallet through an Omni-capable wallet (like omniwallet.org), you’ll be able to see your AMPs there. And while the price during the sale was an average of 182 AMPs per dollar, you’ll see that **you’ve actually received exactly twice that** due to an error we encountered while distributing the AMPs. 

Due to technical issues (see below), a few AMP transmissions were carried out twice during the distribution. The nature of the Bitcoin protocol is that transactions are irreversible, and these tokens could not have been retrieved.

This is, of course, unfair towards our supporters that were not lucky enough to receive these extra tokens, and so we have distributed that same amount to everyone who’s participated in the crowdsale. This is a move that would essentially halve the price of each AMP - while providing all crowdsale participants with twice the amount. 

We have also turned to Craig Sellars, our trustee from Omni who holds the power to issue tokens, so that we can issue double the tokens to all other existing AMP wallets (Bounty Wallet, User Reward Wallet, etc) and maintain perfect equity. This way, **everyone receives the exact same value of AMPs, and the total value and "market cap" of existing tokens remain exactly the same**; the change becomes one in name only, and everyone gets the exact fair share of AMPs. 

Here’s a statement from Craig Sellars, Co-founder and CTO of Tether and Technologist for Omni, our trustee:

==============================

During the Synereo AMP crowdsale token distribution, an error was made which resulted in an incorrect amount of AMPs being sent to several users. The result was that some AMP crowdsale participants received twice as many Synereo AMPs than intended.

 

In consultation with the Synereo team, we decided that there were several options available:

1. Reach out to each user and request that they send back the extra AMPs, hoping to minimize the damage.

2. Grant additional tokens to the other crowdsale participants to match the extra amount received by some participants, such that everyone received the increased amount.

3. Issue additional Synereo AMPs, bringing the total circulation to 2,000,000,000 instead of the originally intended 1,000,000,000, and also do #2 above.

Option #3 was deemed the safest and easiest course of action, and I concur.

 

So as of today, all crowdsale participants have received what amounts to 2x the number of Synereo AMPs than originally purchased, each valued at half the dollar price. All other wallets have been allocated 2x their original number as well, maintaining similar value across the board. 

 

I believe that the course of action chosen represents the best interests of the crowdsale participants - alleviating the problem caused by the technical error. This is why I've decided to authorize the issuance of these tokens, and will proceed to doing so immediately. 

 

As always, you can follow this process as well as keep track of the entire amount of AMPs and their allocation to Synereo’s public wallets through the omnichest service.

I will follow the original course of action committed by the Synereo team, and will agree to destroy the remaining Synereo AMPs set aside for the crowdsale as originally intended.

-- Craig Sellars

==============================

 

We have now finished the distribution of additional AMPs to all wallets belonging to users who participated in the crowdsale, and will soon issue tokens to all other wallets to finalize the allocation as per the logic described above. As always, all information about these wallets is completely transparent and available here:

### [Existing W](http://omnichest.info/lookupsp.aspx?sp=39)[allets](http://omnichest.info/lookupsp.aspx?sp=39):

* [Crowdsale Wallet](http://omnichest.info/lookupadd.aspx?address=3Q7T1ES6atTpeSid3w17HS3eEsHbhQC9jf) 

* [User Reward Wallet](http://omnichest.info/lookupadd.aspx?address=38X3p54WftkmiQmywwzvQzv5ZmbpwWndLL) 

* [Content Creator Wallet ](http://omnichest.info/lookupadd.aspx?address=3594LvBdb7epiJQ3domUH52p3UFMJK7AoW)

* [Founder Reward Wallet ](http://omnichest.info/lookupadd.aspx?address=3AKjXkuBEyaXfuXVfdf1VUBAzGPR49NifM)

* [Bounty Wallet](http://omnichest.info/lookupadd.aspx?address=3No5y1WuEh4LSEFNngyPdEmyMUqS8rBCWb) 

* [Future Funding Wallet](http://omnichest.info/lookupadd.aspx?address=34MWvp1xfxaaqXENxWW45uqDfuNY9f8hr2) 

*Transparency is key. *We will be happy to answer any question you may have regarding the AMP distribution process so that you are satisfied with the solution we’ve implemented.

We are happy to have you with us.<br>

The Synereo Team

*Be Part of the Solution*<br>

##P.S.

###Here's what happened

After testing 5 mini txns which worked correctly, we ran 5 of our actual txn's, which also worked correctly. We then ran:

*screen ./fullAMPMinusFirstFiveDist.sh > AMPDistTxnIds.txt*

to handle the remaining txn's.

The script (fullAMPMinusFirstFiveDist.sh) put a timed delay between each txn, so as not to overwhelm the server.

The *screen* process died, which we believed to indicate that the *script* process died.

We ran a ps to check to see if the *script* process was indeed still running just detached from the *screen* process.

We saw no such process.

We inspected the logs and made a determination as to the last txn the mastercored had successfully completed.

We verified that against the blockchain.

We cut our script into two smaller batches from the point where we believed the *script* process had failed.

We launched the first of the smaller batches and noticed we were beginning to get insufficient funds errors, that's when we discovered the double payouts, and stopped the whole process to figure out what was going on.

###Here's our analysis

Since we never ran the second of the smaller batches, but we confirmed txn's in the blockchain addresses in the second of the smaller batches, what must have happened is the script process kept running even though the screen process died.

However, it must have completed while we were assessing what happened, but before we ran the ps to see if the script process was still in flight.

Then, the mastercored server logs must have been behind in being updated so that what we thought was the last txn completed was out of date.

So, when we restarted we restarted from where we believed it had failed, those txn's were already in flight.

###Here's what we did in response

We have run two independent calculations to make sure we know exactly who was double paid - because we needn't pay them any more AMPs at all.

From these we calculated a new script that pays out a second time to those who were only paid once. Yesterday we ran that script (actually, it was 8 scripts, comprising batches of ~50 txns), and that went off without a hitch.

