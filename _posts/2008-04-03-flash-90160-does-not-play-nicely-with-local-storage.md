---
date: '2008-04-03 18:46:55'
layout: post
slug: flash-90160-does-not-play-nicely-with-local-storage
status: publish
title: Flash 9.0.16.0 does NOT play nicely with local storage
tags: [argh]
categories: [Software]
wordpress_id: '17'
---

OK. So I thought I wasn't crazy.  I reviewed my code.  I tested Dojo versions.  I isolated conditions.  I followed dead-ends in desperation.

And then the problem goes away.  I can't get SharedObject storage to break anywhere (and I'm still not sure why it was broken, then magically fixed -- I suspect an update to the remote machine I was using, since the cluster is monitored/managed).

And then, today, we replicate it in the one place in the world we really care about, and scrape the Flash version: **9.0.16.0**.

So I check if Adobe is benevolent enough to lend a hand (installable old version) to poor developers who are getting hosed.  They give a nice package, so I was thrilled.

Then I fight with the installers/uninstallers for 6 versions until I find a golden nugget: **uninstall_flash_player.exe** **/clean** takes care of the registry entry that was stopping anything but the latest version (as it had already been installed) from running, though they install with "no problems".

And, with undue buildup, the point of this post:

_Flash 9.0.16.0 does NOT work with Dojo Storage 1.1, period._

The good news is that all newer versions do, and 9.16 is coming up on two full years old with 3 major updates since. Time to beg for this lab to be updated and get on with better problems -- like IE's eternal lifetimes of objects created in iframes and its derivative memory leaks. -NB
