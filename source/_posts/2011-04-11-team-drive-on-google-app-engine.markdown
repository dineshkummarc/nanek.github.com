---
author: kenan
date: '2011-04-11 16:11:46'
layout: post
comments: true
slug: team-drive-on-google-app-engine
status: publish
title: Team Drive on Google App Engine
wordpress_id: '326'
categories:
- cloud computing
- development
---

Last year, I created [Team Drive](http://funddrive.appspot.com) on [Google App
Engine](http://code.google.com/appengine/).  I wanted to learn about Google
App Engine (GAE) which is a hosting platform for python/java based
applications.

Team Drive is based on a site that Fabien built years ago to record donations
of items for a charity food drive.  Users from an organization are split into
separate teams, and then compete to see who can collect the most food items.
By adding this friendly team competition to a normal food drive, you can
increase the participation and results of the drive.

Building on GAE is quite different than traditional single server application
deployments.  Everything in App Engine forces you to think about how to scale
your application.  By placing constraints, such as a thirty second processing
limit per request, it forces you to think about approaching problems
differently than if you were writing this to run on a single server.

App Engine supports two types of authentication methods, Google Accounts and
OpenID.  If you want to leverage their session management you need to use one
of these.  For an site aimed at organizations, I didn't want users to have to
create a google account or OpenID.  To work around this I implemented an
OpenID provider in the application.  Administrators could upload a list of
email addresses and a Team Drive OpenID would be created for each of these
users.  The users themselves don't need to know that they are using OpenID, as
I only ask for their username and password.

Another example is for counting the number of items contributed by a person,
team, organization or type.  In a relational database you might just sum these
up on demand.  However using the Google datastore you generally store counts
on the object itself and increment this count on each update.  App Engine has
also provided an implementation of map/reduce that makes it easy to perform
operations such as sums or counts over large collections.

