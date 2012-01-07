---
author: kenan
date: '2009-10-13 09:06:06'
layout: post
comments: true
slug: security-tools-for-net-development
status: publish
title: Security Tools for .NET Development
wordpress_id: '209'
categories:
- development
tags:
- .NET
- security
---

Security is a programmer's responsibility.  Your project manager or client is
not going to ask for security, but it is a basic implied requirement for any
software project.  A good place to start is to look at the [top ten common
vulnerabilities](http://www.owasp.org/index.php/Top_10_2007).  Think about how
many of these might affect your current project.  Odds are if you have not
consciously though about security, then your application is likely vulnerable.

Since I recently started writing a lot more .NET based applications I have
come across two useful tools for assisting in providing application security.
Even if you are careful to validate all application inputs, it is still useful
to validate your work using these tools.

[Anti-XSS](http://www.microsoft.com/downloads/details.aspx?familyid=051EE83C-
5CCF-48ED-8463-02F56A6BFC09&displaylang=en) - a library that can help sanitize
inputs to help protect from cross site scripting attacks. [
CAT.NET](http://www.microsoft.com/downloads/details.aspx?FamilyId=0178e2ef-
9da8-445e-9348-c93f24cc9f9d&displaylang=en) - a Visual Studio plugin that will
do code analysis to help identity cross site scripting and SQL injection
vulnerabilities.

It is a good idea to set up security scans has part of your project build
steps with a [continuous integration
server](http://techopener.com/blog/2009/10/continuous-integration-with-
hudson/).

