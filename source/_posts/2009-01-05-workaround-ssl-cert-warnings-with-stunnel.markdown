---
author: kenan
date: '2009-01-05 20:00:00'
layout: post
comments: true
slug: workaround-ssl-cert-warnings-with-stunnel
status: publish
title: Workaround SSL cert warnings with stunnel
wordpress_id: '81'
categories:
- development
- tools
---

On occasion I find myself attempting to programatically make a HTTP request
over SSL, however it gives connection warnings such as expiration or name
mismatch which causes the request to fail.  You could update the server
certificate, however this can be a pain.  An alternative is to use stunnel.
Install it, set it up to accept traffic on a port and then forward that
traffic to the SSL site.  Your client can then connect over http to the
stunnel port, and stunnel will forward this request to the SSL site ignoring
the warnings.  There are a number of other uses for stunnel, so check it out,
if your working with SSL.

[http://www.stunnel.org/](http://www.stunnel.org/)

Example config file below:

    
    client=yes
    verify=0
    [psuedo-https]
    accept  = 8080
    connect = yourhost:443
    TIMEOUTclose = 0

