---
date: '2008-10-25 18:31:59'
layout: post
slug: adium-logs-make-it-very-slow
status: publish
title: Adium logs make it very slow
categories: [Miscellaneous]
wordpress_id: '22'
---

Hypothesis confirmed: with logging on, Adium gets to be _very_ heavy.

I was seeing somewhere between 30 seconds and a minute to get to the keychain login, and another 30 seconds to bring up a contact list. Clean out the logs, relaunch -- about 4 seconds for each.

The logs live in `~/Library/Application Support/Adium 2.0/Users/Default`. Remove or archive them and watch it fly. -NB
