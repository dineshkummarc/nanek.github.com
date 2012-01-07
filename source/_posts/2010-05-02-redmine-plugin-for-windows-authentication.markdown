---
author: kenan
date: '2010-05-02 19:36:16'
layout: post
comments: true
slug: redmine-plugin-for-windows-authentication
status: publish
title: Redmine plugin for windows authentication
wordpress_id: '284'
categories:
- development
---

Redmine.org is an open source project management application. It is simple to
setup and works great. It supports LDAP authentication out of the box. We
recently setup Redmine for a project to run behind IIS using fastcgi and
wanted to automatically login using windows authentication. We didn't see a
option for this, so I created a simple plugin that can be used to add this
functionality.

http://github.com/nanek/redmine_windowsauth

