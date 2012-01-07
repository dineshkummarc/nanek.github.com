---
author: kenan
date: '2009-04-02 22:45:16'
layout: post
comments: true
slug: windows-services-crash-after-restoring-from-standby-mode
status: publish
title: Windows services crash after restoring from Standby mode
wordpress_id: '169'
categories:
- troubleshooting
tags:
- windows
---

Recently Windows Update applied SP3 to XP on my Dell Latitude D630. I was
pretty sure I already installed SP3, but I applied it anyway, what could it
hurt right?

Well...every time I restored from Standby mode, my network services, firewall,
sound and a number of other services stopped working. Most notably was the
sound, and after further investigation I noticed the rest. Odd flickering of
the windows theme also cued that something was out of whack. I first thought
it might be related to a virus or Conficker, however after triple checking and
re-scanning everything nothing came up.

Looking further, windows has all of these services running under the same
svchost.exe process. Therefore when one of these crashes, it takes down all of
them. Below is a list of the services Windows runs as a shared process on my
machine: AudioSrv,BITS,Browser,CryptSvc,Dhcp,ERSvc,
EventSystem,helpsvc,lanmanserver,lanmanworkstation,Netman,Nla,RasMan,
Schedule,seclogon,SENS,SharedAccess,ShellHWDetection,TapiSrv,Themes,
TrkWks,w32time,winmgmt,wuauserv,WZCSVC

Turns out you can modify these services to run their own process, which would
allow me to determine which service is causing the problem. From the command
prompt: sc.exe config ServiceName type= own You need the space between the "="
and "own". This command will cause the service to always launch in its own
svchost. To revert the service back to its original state, run the following
command from the command prompt: sc.exe config ServiceName type= share

After setting this and restarting the services I went into Standby to
reproduce the issue. This time nothing crashed except for the Wireless Zero
Configuration service. Now that I have narrowed it down, I did some more
searching and found [http://support.microsoft.com/kb/951447](http://support.mi
crosoft.com/kb/951447) which says to disable the the power management features
on the Wireless Network Connection. Makes sense, so I give it a try. Go into
Standby, startup and then immediate blue screen of death.

Taking a look at the wireless drivers reveals they are pretty old, so a quick
search for the Intel 3945ABG wireless driver reveals some recently released
[driver
updates](http://downloadcenter.intel.com/Product_Filter.aspx?ProductID=2259).
With these updated drivers I don't get a blue screen, however I still have the
issue of the Wireless Zero Configuration service crashing.  Luckily this
service isn't necessary as Intel provides Wireless connection software.  Also
the service can be started once it fails if needed.  However it is a bit
annoying.  Even though I didn't completely resolve this issue, I do think the
troubleshooting steps that were taken would be useful in other similar
situations.

