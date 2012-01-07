---
author: kenan
date: '2009-12-22 21:47:50'
layout: post
comments: true
slug: foursquare-on-windows-mobile
status: publish
title: Foursquare on Windows Mobile
wordpress_id: '266'
categories:
- development
- mobile
tags:
- foursquare
- mobile
---

[Foursquare ](http://foursquare.com)does not have a windows mobile version of
their application, so I thought it would be a great opportunity to try and
build an app.

Things that are working fairly well:

  * Foursquare API access.
  * JSON.NET is used to parse the JSON responses.
  * sqlite is used for caching http responses.
  * OAuth is used for authentication to foursquare.
  * GPS lookup.
Things that don't work and have proved difficult to implement:

  * Responsiveness.  At times the app stops responding and overall feels too slow for normal use.
  * Cell ID lookup.  This is important as GPS often does not work indoors.  It appears access to this API may be protected on most phones.
  * Good looking user interface.  Plus dealing with different phone resolutions, orientations, and sizes makes it a little more complicated.
Things that would be interesting to implement but require a solid base
application:

  * Map integration
  * Integration with other API's such as Yelp
You can find the source at
[http://foursquare.codeplex.com](http://foursquare.codeplex.com) along with a
CAB for installation on your phone if you want to try it out.  Look under the
planned download section.  It works ok on my HTC Touch Pro.  If you are
interested in contributing to this effort, let me know.  I'm debating spending
more time on making this work better or building a HTML5 based mobile web
application.

