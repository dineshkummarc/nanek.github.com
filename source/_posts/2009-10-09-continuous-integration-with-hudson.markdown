---
author: kenan
date: '2009-10-09 08:10:00'
layout: post
comments: true
slug: continuous-integration-with-hudson
status: publish
title: Continuous Integration with Hudson
wordpress_id: '208'
categories:
- development
tags:
- continuous integration
- hudson
---

Recently I came across [Hudson](https://hudson.dev.java.net/), an open source
[Continuous Integration](http://en.wikipedia.org/wiki/Continuous_integration)
server.   I often hear about cruise control, however it always seemed like it
would be difficult to get setup.

A Continuous Integration server can help you automate tasks in your
development life cycle.  It will checkout a project from your source code
repository, build it, and run any number of additional tasks that you can
configure.  For example, it can run unit tests that you have written for your
project.  Another example would be to configure [StyleCop
](http://code.msdn.microsoft.com/sourceanalysis)or FxCop to analyze your
source code against various rules.  All of these tasks are completed on a
build server automatically and any issues are delivered through the UI, email,
or RSS.  This instant feedback loop will make you and your team members spot
any issues sooner and make you a better programmer.

Some things that make Hudson in particular stand out:

  * It can build [.NET](http://redsolo.blogspot.com/2008/04/guide-to-building-net-projects-using.html) and Java applications.
  * To get started you just run the jar, or deploy to tomcat.  No db or other configuration to install.  It can even install itself as its own service.
  * Lots of plugins.  Plugins that you can install from within the application just like WordPress.
  * User interface is simple and clean.
  * It just works.
Bottom line, take 10 minutes and check it out.  Let me know if this is not the
best Continuous Integration server for Java and .NET.

