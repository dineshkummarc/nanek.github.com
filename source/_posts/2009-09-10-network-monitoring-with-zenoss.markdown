---
author: kenan
date: '2009-09-10 08:00:16'
layout: post
comments: true
slug: network-monitoring-with-zenoss
status: publish
title: Network Monitoring with Zenoss
wordpress_id: '194'
categories:
- tools
---

Recently I configured [Zenoss](http://www.zenoss.com/) for a client to allow
them to be more proactive and receive email notifications when a service or
server goes down on their network.  When you are frequently upgrading or
modifying applications there are bound to be issues that crop up and cause
failures.  It is best to be aware of these and correct them before your users
notice.

To get started you can download a Virtual appliance with Zenoss already
installed.  Once it is up and running, you will want to install a few ZenPacks
that are relevant to your environment.  These are basically just extensions to
the product that can give you more specific collection and reporting tools.
The next step is ensure there is an SNMP agent running on the machines you
plan to monitor.  SNMP is a common network monitoring protocol and an basic
agent comes with Windows.

Once you have the basic ZenPacks and SNMP running you can have Zenoss discover
all your servers and network devices, or you can add individual servers as
needed.

Zenoss will model each device, determine what software, services, ports, disk
drives are on the device and assign default thresholds and alerts to each.
For example if a disk drive is more than 90% of capacity it will create an
event message.  These messages will start displaying in nicely color-coded
dashboards for now.  The next logical step is to setup email notifications by
defining alert rules per user or group.  Alert rules allow you to filter the
event messages and only receive the ones that are important to you such as
only Production systems that throw Error messages.

If you are in need of a monitoring solution, I highly recommend you give
Zenoss a try.  It really is quite easy to setup and has a vibrant community
behind it with a lot more advanced capabilities than I have discussed here.
Also take a look at a ramp up video put together by JumpBox for Zenoss at
[http://vimeo.com/6408567](http://vimeo.com/6408567).

