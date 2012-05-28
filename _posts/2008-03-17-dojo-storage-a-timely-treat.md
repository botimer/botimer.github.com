---
date: '2008-03-17 20:16:25'
layout: post
slug: dojo-storage-a-timely-treat
status: publish
title: Dojo Storage — A timely treat
categories: [Sakai, Software]
wordpress_id: '14'
---

Every so often, something goes your way, ya know? So, last Thursday, I posted to sakai-dev asking whether I should use dojox.storage or borrow some stuff from rWiki:

[http://www.nabble.com/Flash-storage----dojo.storage-or-homebrew--td16033853.html](http://www.nabble.com/Flash-storage----dojo.storage-or-homebrew--td16033853.html)

It also just so happens that the main guy behind dojox.storage, Brad Neuberg, apparently felt like being a kind soul, did a ton of refactoring work, and bundled up the smallest, most practical package possible for my immediate need and posted it, not three hours later:

[http://codinginparadise.org/weblog/2008/03/easy-download-of-dojo-storage-for.html](http://codinginparadise.org/weblog/2008/03/easy-download-of-dojo-storage-for.html)

So far, it's really easy to use (about 15 total lines, and tastes like HashMap) and moves between browsers very well. I'm only having one issue on IE. It's choking on line 52 of some unnamed file that a little Googling hints is related to the Flash plugin.  (For the curious, it's an Object Required error in __flash__removeCallback()...)

I guess this can happen with different ways of including SWF files -- the confusing bit is that one thread says use the HTML embedding, rather than JavaScript, and another says to use JavaScript rather than HTML. The tricky part is that both seemed to fix it.

So, I'm going to test on a machine that doesn't have script debugging turned on and hope for the best. If it doesn't grumble too badly, I'll poke around for a fix in my spare time.

Either way -- Cheers, Brad! You really made my day. -NB
