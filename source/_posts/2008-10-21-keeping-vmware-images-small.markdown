---
author: kenan
date: '2008-10-21 22:42:18'
layout: post
comments: true
slug: keeping-vmware-images-small
status: publish
title: Keeping VMWare images small
wordpress_id: '7'
categories:
- virtualization
tags:
- virtualization
- vmware
---

Virtualization technology is used everywhere these days.  It really has
changed the way I work and provides a number of advantages over traditional
tools and methods.  I've created a library of VMWare instances with different
products installed on each to avoid bogging down my laptop.

One difficulty I often run into is the size of vmware images can quickly
become quite large.  Which in turn makes transfering them across the network
to coworkers slow and painful.  Below are some tips on how I keep vmware
instances down to a reasonable size.

  * Remove service pack uninstallers c:\windows\$NT*  (leave $hf_mig$)
  * Move c:\i386 to a common share not on the VM
  * Remove files inside C:\Windows\SoftwareDistribution\Download
  * Remove any other unneeded files, such as installers, log files (I use [WinDirStat](http://windirstat.info/) to find large files)
  * Empty the recycle bin
  * From disk cleanup, advanced turn off the pagefile.sys and restart the vm
  * Shrink the image using the vmware tools (you will need free space on your host machine the size of the image)


<img alt='VMWare Tools Shink Menu' src='/images/vmware_tools_shrink.png' width='300px' height='261px'/>

If you have any other tips on how to manage vmware images, please post them in
the comments!

