---
date: '2009-07-25 23:27:18'
layout: post
slug: sakai-jsonp-callbacks-in-entity-broker
status: publish
title: Sakai JSONP callbacks in Entity Broker
wordpress_id: '24'
tags:
- entity broker
- json
- mashup
- Sakai
categories: [Sakai, Software]
---

So, I'm going to try to get back in the habit. I owe Ray two posts, so this is a warmup. Anyway...

I've just added JSONP callback support to Entity Broker. This allows you to make a data feed that can be used for mashups. The normal JSON feeds don't allow for this because, when the script tag is added, the object literal just drops into the ether -- it needs to be handed off to a function. Plenty of others are using this technique now and it's well supported in things like jQuery; just search around.

The important bit is that you can either use the default callback function (jsonEntityFeed) or specify your own. You just craft a URL to the entity and optionally give a parameter. For example:
`
http://sakai/direct/entity-prefix/some-id.jsonp
http://sakai/direct/entity-prefix/some-id.jsonp?jsonCallback=myCustomCallback`

If you are using jQuery, you can use the getJSON method to call an inline, unnamed callback like this:
`
$.getJSON('http://sakai/direct/entity-prefix/some-id.jsonp?jsonCallback=?',
    function(data) {
        alert(data.whatever.element[0].here);
    });
`

It's all pretty straightforward and tracked in [SAK-16757](http://jira.sakaiproject.org/browse/SAK-16757). I imagine that this will get tagged at some point, but it's just in trunk for now. Happy Hacking! -NB
