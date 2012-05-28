---
date: '2008-10-02 19:14:52'
layout: post
slug: php-json_encode-is-quirky
status: publish
title: PHP json_encode is quirky
wordpress_id: '21'
tags: [php, json]
categories: [Software]
---

So, amidst an interesting fight with CakePHP, I was fortunate enough to spot a
quirk in [`json_encode`](http://php.net/json_encode) when passing arrays. If
you have a typical ordinal array, life is good. If you have a typical
associative array, life is good. The quirk is in how PHP decides what you have.

_We define "life is good" here as: you pass something without meaningful keys,
you get an array; you pass something with meaningful keys, you get an object._

When you have a regular old array of values (or rows of a result set, in my
case) and you filter it with, e.g.,
[`array_filter`](http://php.net/array_filter), you can end up with holes in the
ordinal numbering.  This delights [`json_encode`](http://php.net/json_encode),
which displays its exceptional, "just works" intelligence, giving you an object
full of numeric indexes pointing at what you thought would be unnamed items in
an array.  In some cases, this makes no difference but, in some, it can be a
big problem.

Fortunately, I'm generally in tune enough with the stylings of PHP that I went
straight to trying [`array_values`](http://php.net/array_values) -- and now,
all is right with the world. Just wrap any
[`array_filter`](http://php.net/array_filter) calls with
[`array_values`](http://php.net/array_values) if you plan to turn the goods
into JSON. -NB
