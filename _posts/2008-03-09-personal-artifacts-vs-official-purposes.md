---
date: '2008-03-09 18:15:29'
layout: post
slug: personal-artifacts-vs-official-purposes
status: publish
title: Personal artifacts vs. official purposes
categories: [Sakai, Thoughts, ePortfolios]
wordpress_id: '11'
---

How long should personal artifacts submitted in some official capacity be
viewable (by learner or official) in their original state? How we can let
learners really own their materials?

We've approached this problem to date by ignoring it. We make an explicit step:
at some point, we force to student to say "I'm done with this thing and it's
yours forever", and lock it. Or we just let it be malleable forever.

This is directly analogous to how, in logic, math, and computer science, we
sometimes restrict input to maintain a lower conceptual threshold. Persistence
and security of artifacts is a really hard problem, so we make sure it can't
destabilize the easier ones we're solving, by distilling a complex grey
gradient into blacks and whites.

It's a perfectly valid way to get a foundation, but it's time to move into our
version of second-order logic -- versioned, purpose-stamped, multi-threaded
artifacts -- to address our complex realities. We can't lie to ourselves and
believe that hard-locking a student's file forever is practical in a personal
learning experience.

The specific thought that triggered this post was that the notion of estimated
secure lifetime in cryptography is relevant to visible/storage lifetime in
ePortfolios. However, this post also includes thoughts on the concepts of fluid
artifacts being copied and made concrete at submission time, and how this
relates to our existing web/email usage patterns.

Lots more below the break.

<!--more-->

### Useful Lifetime


In cryptography, there is a notion that the encryption should be strong enough
that the estimated time to break it is longer than the sensitivity of the
information. There is a general acceptance that, if it's possible to decrypt
the message legitimately, then someone could do it illegitimately.

We just try to make sure that it would take a suitably long time (a few years
to steal a single credit card number from an intercepted e-commerce
transaction, for example). Security of physical safes is similarly rated on
estimated and actual time to crack by an expert.

It seems to me that we should consider the "useful lifetime" of submitted
versions of user data in Sakai and ePortfolios. It's kind of the inverse, where
it's not the notion of how long it'll take the bad guys to get in, but the
notion of how long the good guys can get in, and for what purposes, before the
thing fades away.

I don't think this will lead a simple answer, but accepting that the valuable
lifetime isn't "forever" seems to be a start. Automatic, timestamped copies
with a defined lifetime for a specific purpose is a tractable scenario. And it
gives institutions a cutpoint to say when data can be archived and/or deleted
from their live systems. Defining when the stuff goes from mutable to
snapshotted -- with a sensible UI -- is the tricky part.


### Metaphors Already In Use


There is one application people employ every day that doesn't seem to get much
attention for its parallels to this problem: **email**.

Lacking sophisticated, intuitive software to collaborate on living information,
people unconsciously send emails containing the two critically differentiable
components: **links** and **attachments**.

	
 1. Links refer to some live resource that could change between the time the
    email went out and when it's consumed. Unless the recipient manually
    archives the resource, they have no reasonable expectation that it will
    remain unchanged. They might be annoyed if a link goes dead or an article
    is deleted, but the effect of visiting a link is understood in the context
    of time-sensitivity. (Just grab a magazine from 2000, try the URLs you find
    and see what happens...)
 2. Attachments are concrete manifestations of things that were alive until
    "Send" was pressed. If the recipient is on vacation or sabbatical for two
    months, the resource waits, patiently, unchanged in the inbox. Emails with
    attachments are, themselves, unaffected by the passage of time. (Look at a
    JC Penny catalog from 1980; all of the information is outdated, but intact.)


As soon as we move away from this familiar, learned metaphor of email, all
sanity breaks down. In a learning system or ePortfolio, we get frustrated when
resources are locked; we get frustrated when they change. We can't seem to make
any sense of the balance between personal rights and abilities, and the
official or accountability needs.

For the system / builders, accountability wins, because accountability pays the
bills. _See [my post on this within Sakai]({{BASE_PATH}}/posts/2008/03/09/sakai-and-osp-development-accountability-personalization)._

For the users, it continues to be a painful problem and they end up saying
things like "I'll just make a document and email it. At least that's simple and
I know what I'll get."

We never realize that the users are telling us what they need -- we just need
to implement it in the system in a way that isn't onerous.

In reality, I think the users need to give an inch and the system needs to give
a mile. The digital world is moving toward versioning, so there is some user
adaptation needed. But we can't force-feed a "better way".

At least ten or twenty aspects of learning/portfolio systems depend on getting
this right. And _right_ means _easy_.

The only thing we should add to the user's world is the ability to make a tag
(in the source control parlance) in some specific spot or make a live link.  I
think switching a connection between the live version and a tagged version is
actually the critical user component, but it must be trivially simple.

I suspect "locking" workflow steps could be implemented as automatic tagging.
Those autotags would be identical save for lasting for a specific period, being
visible to others based on appropriate rules, and not convertible/detachable.

I'm naively hopeful that the mainstreaming of versioning (in Google Docs,
"Track Changes", wikis, source control, document management systems, JCR, etc.)
will give us all some internal understanding of how digital information exists
infinitely -- as opposed to the discrete physical counterparts -- and how to
manage it. Don't laugh just yet -- you don't think about your understanding of
emailing links vs. attachments; you just do it.

One very interesting thing I've noticed in Google Docs: there are automatic
drafts that happen while authoring, and you can switch between them at leisure
until you save. Then the interim, uninteresting junk fades from view -- a
sophisticated technique to maintain sanity in the user's world.

I'm not sure why the topics of cryptography and email haven't come up in this
conversation. I just hope that considering what people use and do implicitly
every day gives us some traction on a practical set of solution strategies. -NB
