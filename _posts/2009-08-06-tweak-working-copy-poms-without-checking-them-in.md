---
date: '2009-08-06 13:04:15'
layout: post
slug: tweak-working-copy-poms-without-checking-them-in
status: publish
title: Tweak working copy POMs without checking them in
wordpress_id: '26'
tags:
- maven
- pom
- poms
- Sakai
- subversion
- svn
categories: [Sakai, Software]
---

A handy little snippet... This is something I've used a few times when I'm
hacking in a working copy and need to change POMs for some local reason
(usually versioning) but can't check them back in modified. I'd like to tweak
the POMs, work on other stuff, build/test, check everything _but_ the POMs in,
rinse and repeat. Here's a workaround:

{% highlight bash %}
$ svn st | grep '^M' | grep [ \/]pom.xml' | sed 's/^.......//' | \
  xargs -I{} svn diff {} > pom.patch
$ svn st | grep '^M' | grep [ \/]pom.xml' | sed 's/^.......//' | \
  xargs -I{} svn revert {}
$ svn ci -m 'whatever'
$ patch -p0 < pom.patch
{% endhighlight %}

Happy hacking. -NB
