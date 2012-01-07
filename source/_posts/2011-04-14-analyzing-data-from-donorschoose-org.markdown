---
author: kenan
date: '2011-04-14 12:28:38'
layout: post
comments: true
slug: analyzing-data-from-donorschoose-org
status: publish
title: Analyzing data from DonorsChoose.org
wordpress_id: '343'
categories:
- tools
---

DonorsChoose.org is running a [contest](http://www.donorschoose.org/hacking-
education) by opening up its data for analysis and use in innovative
applications.  They have provided data dumps for project, search, donation and
gift card data in large csv files.  There are a two free tools that I
recommend to quickly review this data.

[Google Refine](http://code.google.com/p/google-refine/) allows you to filter
the data and identify data quality issues.  It also makes it very easy to
manipulate and transform the data any way you like.  Bulk replacements and
column transforms are two of its strengths.  Another cool feature is the
ability to template exports into different formats such as JSON.  Heres some
tips I found with working with the Donors Choose data.  First increase the
[memory settings](http://code.google.com/p/google-
refine/wiki/FaqAllocateMoreMemory).  Second, update the [facet limit
setting](http://code.google.com/p/google-refine/issues/detail?id=31#c6) to
something higher.  The [screencasts](http://code.google.com/p/google-refine/)
for Google Refine do a great job in demonstrating its use.

[Google Fusion Tables](http://www.google.com/fusiontables/) is good for
visualizing data in various ways like charts, maps, or timelines.  This tool
works better with data sets that are already cleaned up.  It takes some time
to load the data and process it, so it is best served for working with just a
slice of data that you would like to present for a specific purpose.  It does
have a 250mb limit per user and a 100mb limit per csv file.

So go ahead and start analyzing this data.  It is for a good cause and the
lucky contest winner will get to meet Steven Colbert!

