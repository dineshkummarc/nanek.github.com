---
author: kenan
date: '2008-12-03 22:37:11'
layout: post
comments: true
slug: sharepoint-development-net-build-events
status: publish
title: Sharepoint development .NET build events
wordpress_id: '57'
categories:
- development
tags:
- .NET
- Sharepoint
---

When developing .NET applications, particularly Sharepoint applications you
might find yourself updating the GAC (Global Assembly Cache) and restarting
IIS a lot.  This can be time consuming if you are making a lot of short
interations in your development cycle.  Below are two steps you can take to
automate this and minimize your wait time.

First instead of restarting IIS using iisreset, we can restart just the app
pool we are working with.   Just add the following commands to you pre build
event of your project.  I add it to the pre-build instead of the post build,
because if I attempt to build before restarting the app pool then it will
often error complaining that .NET has it locked.  In order to give the restart
command time to run before the build starts, the next command functions as a
wait for 5 seconds.

cscript c:\windows\system32\iisapp.vbs /a "SharePoint - 80" /r

ping -n 5 127.0.0.1 > NUL 2>&1

When needed, I also update my project post build event to add my new dll to
the GAC with this command.

gacutil -if "$(TargetPath)"

You can find gacutil.exe under C:\WINDOWS\Microsoft.NET\Framework\v1.1.4322
(you dont have to be using 1.1) and move it to c:\windows\system32 so that it
can be found.

[![buildevents](/images/buildevents.png)](/images/buildevents.png)

