---
date: '2008-11-23 16:59:06'
layout: post
slug: aptana-vista-php-oracle-xe-victory
status: publish
title: Aptana + Vista + PHP + Oracle XE == Victory!
wordpress_id: '23'
tags:
- aptana
- oracle
- php
- vista
- windows
categories: [Software]
---

So, I'm doing some development against Oracle with PHP and really wanted
[Express Edition](http://www.oracle.com/technology/products/database/xe/index.html) on a
local machine to be able to hack without a lot of messing around (my other
Oracle instances are behind VPNs, etc.)  I've also been thinking about hooking
my desktop back up for one of those environment changes that results in a
productivity boost.  A third factor is that I want to do this development in
[Aptana](http://aptana.com/studio) because, well, it's just plain sweet. 
Easily said...

<!--more-->

...and pretty easily done once the steps are laid out.

The Aptana Studio and XE installs were both cake.  I love that, however it has
come about, "just works" is finally taking hold across all three big
platforms.  I also highly recommend
[SQL Developer](http://www.oracle.com/technology/products/database/sql_developer/index.html)
(so far, anyway.)  For anyone who's worked extensively with SQL Server 2000,
this thing feels like Query Analyzer, and I couldn't be happier.

So, what's the problem?

Well, Aptana has that very slick integrated PHP instance, and I don't plan to
do anything beyond that... but it doesn't ship with the Oracle extensions. 
After enough poking around, I was pleased to find that the extensions are
stored in one of the Aptana plugin directories, and the php.ini files are
there, too.  This just leaves getting the DLLs and dropping/enabling them.

To get to the goods, assuming Aptana and XE are installed:
	
 1. Download [php_oci8.dll](http://pecl4win.php.net/ext.php/php_oci8.dll) and
    [php_pdo_oci.dll](http://pecl4win.php.net/ext.php/php_pdo_oci.dll) from
    [PECL4WIN](http://pecl4win.php.net/index.php). (Aptana 1.2 ships PHP 5.2.5, so
    grab 5.2)
 2. Drop these into `...Aptana Studio\plugins\com.aptana.ide.php.interpreters.win32.x86_5.3.14.v20081007\resources\php5\ext`
 3. Add your extensions to the php.ini files in `...resources\php_xdebug` and `...resources\php_zend_debugger`

That's it.  Now you can connect to Oracle instances.  I, personally, prefer
PDO, so included the driver in the directions.  You wouldn't need this if you
were doing raw OCI.  For a cheatsheet, the connection looks like this:
`$dbh = new PDO("oci://host/SID", "user", "pass");`  With a local XE, the
default would be `//localhost/xe`.  I hope this saves someone the couple of
hours I spent messing around. -NB
