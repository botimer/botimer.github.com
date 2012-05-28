---
date: '2008-03-09 13:50:26'
layout: post
slug: eclipse-ganymede-34-still-no-visual-editor
status: publish
title: Eclipse Ganymede (3.4) - Still no Visual Editor?
tags: [eclipse, java, netbeans]
categories: [Software]
wordpress_id: '8'
---

About a year ago, I was anxious that an upgrade from the [Visual Editor Project](http://www.eclipse.org/vep/WebContent/main.php) might be included in the Eclipse Europa (3.3) release...

I'm a big fan of the portability, speed, and general native feel of SWT, and I'm generally a fan of the Eclipse setup. I've also done a good bit of C# stuff for hacking out GUIs for one-off apps. It's actually easier than dealing with console scripts and you can hand off an .exe to let someone accomplish something without a proper shell. Given that working with Sakai is pretty Java-intensive, and that I was bouncing between OSX/XP, I figured these lightweight admin-style GUIs could be hacked together in SWT... Boy, was I wrong.

I admire the complexity of a GUI builder that generates all kinds of layout code, etc. It's definitely not something I want to take on as a project right now.  But, I'm pretty frustrated with the VEP. It missed the Europa bundle -- no big deal, I thought -- "there'll be a package soon enough; this is important stuff".  Along comes October (three full months later), and this is posted on the main page:


![Visual Editor + Europa == ouch]({{ BASE_PATH }}/images/2008/03/vep-notice-narrow.png)


To my knowledge, this is the only official status update from the VEP since. While scraping the blogs and forums, I found one guy who seems to be maintaining unofficial builds, but I don't see any active development at all.  If you're dangerous, you can check out [http://www.ehecht.com/eclipse_ve/ve.html](http://www.ehecht.com/eclipse_ve/ve.html) -- he even has a Ganymede M3-compatible bundle -- I'm too <del>scared</del> <del>disinterested</del> busy to spend the time.

And now that NetBeans has released 6.0 with cleaned up usability and the actually-funded Matisse, I'm really starting to wonder if I should give it another look. Another really cool feature I saw demoed was live model diagrams with full round-tripping right in the IDE. And they seem to have a BPEL designer integrated, which tickles my SOA side.

I'm not giving up on Eclipse, but I treat free software kind of like free agency: I use and probably contribute to what works for me. The adoption/switching cost is based on learning/porting time and, for an IDE, I figure that to be about two weekends of hacking to get productive. If I can crank up and save a few hours at a crack by being able to whip up a GUI and evolve a new data model with autodiagrams, it's pretty tempting. -NB
