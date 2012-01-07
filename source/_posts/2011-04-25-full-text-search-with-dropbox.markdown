---
author: kenan
date: '2011-04-25 18:58:20'
layout: post
comments: true
slug: full-text-search-with-dropbox
status: publish
title: Full Text Search with Dropbox
wordpress_id: '359'
categories:
- development
- tools
---

[Dropbox](http://db.tt/BKfYgZE) + [Solr](http://lucene.apache.org/solr/) =
full text indexing and search for files in your Dropbox. I wrote an app in
[Sinatra](http://www.sinatrarb.com/) that authenticates to Dropbox, downloads
your files, and indexes them in Solr. It also provides a simple interface for
searching that includes hit highlighting and some basic facet support.

[![Search Dropbox](/images/searchdropbox.png)](/images/searchdropbox.png)

I've posted the project on [github](https://github.com/nanek/searchdropbox),
so feel free to download and try it. For anyone interested in this as a hosted
service instead of as a download and install, let me know.

