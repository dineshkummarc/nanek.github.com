---
author: kenan
date: '2008-10-27 20:42:38'
layout: post
comments: true
slug: 5-reasons-to-use-openid-with-enterprise-saas
status: publish
title: 5 reasons to use OpenID with Enterprise SaaS
wordpress_id: '16'
categories:
- openid
tags:
- enterprise
- openid
- SaaS
---

As employees use more and more applications outside corporate network
boundaries traditional identity systems start to break down.  Example business
applications that fit this description are [Google
Apps](http://www.google.com/a), [Microsoft Online
Services](http://www.microsoft.com/online), [Zoho](http://zoho.com),
[Salesforce](http://www.salesforce.com), [ADP](http://www.adp.com),
[WebEx](http://www.webex.com), [QuickArrow](http://www.quickarrow.com) to name
a few.  Luckily OpenID can step in and provide a great experience for IT
administrators and end users.  [OpenID](http://openid.net) is a web
authentication protocol based on open standards.

Currently end users have to create new accounts at each of the sites above,
much like early days of the enterprise when you had to create a new account
for each application until SSO solutions came along.  Creating new accounts is
not only a pain for employees but perhaps even more so to IT administrators
that need to manage these accounts.  Below are 5 reasons to create a corporate
OpenID provider instead of having your users create new accounts:


**Account creation and removal** = Normally users have to create a new account at each site.  When a user leaves the organization they could potentially still have access as they created the account, unless you have a good process in place to deactivate accounts.  OpenID can be integrated with your existing user repository such as Active Directory or LDAP so that when accounts are deleted they can no longer be used.  
**Authentication method** = Since you control the OpenID provider, you can control the authentication method.  You can use different methods such as Username/Password, InfoCards, SSL Client Certificates or Tokens.  
**Password Managment** = When web applications outside your organization control the account, they might not have as robust password management features which places more responsibility on your employees.  When you control the authentication using OpenID, you can set your own password policies and there is only one password that the user needs to remember.  
**Company branding and identity, naming conventions** = OpenID uses a URL as a users identity, therefore you can include your company name, such as http://user.company.com.  This allows you to set a standard naming convention that is consistant throughout your organizations, much like your email addresses are.  
**User experience** = Users only have to remember one account.  

An example is Sun, they have setup a OpenID for their employees at
https://openid.sun.com

Please leave your thoughts in the comments!

