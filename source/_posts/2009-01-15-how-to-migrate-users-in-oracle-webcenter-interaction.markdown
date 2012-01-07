---
author: kenan
date: '2009-01-15 23:11:55'
layout: post
comments: true
slug: how-to-migrate-users-in-oracle-webcenter-interaction
status: publish
title: How to migrate users in Oracle Webcenter Interaction
wordpress_id: '94'
categories:
- development
tags:
- webcenter
---

Webcenter Interation provides great tools for importing users from external
user directories.  Depending on your user directory and configuration you set
a unique identifier to use that is often not the username.  I have ran across
a few senarios in which you want to switch to a different user directory
without losing any user settings or preferences.

Most commonly, you might have a production Active Directory server that a
production portal syncs with and a development server that syncs with a
development Active Directory server.  Now lets say you migrate your production
portal database to your development environment.  There are a number of items
you have to fix for it to operate in this new environment.  Take a look at
[ALUI Administration Tool for Environment Refresh: String Replacing for
URLS](http://fsanglier.blogspot.com/2008/01/alui-administration-tool-for.html)
for more information regarding syncing environments.  For the purpose of this
post, we are just concerned about the users and keeping their settings,
preferences and security throughout the portal.

In our case, a users Active Directory ObjectGUID is their unique identifier
and by definition this is different in each Active Directory server (unless
they are in the same domain of course).  So if we just sync with the
development Active Directory server, the portal would delete all of the users
and then recreate them even though the usernames are the same.  Below are some
steps I have successfully used in the past to avoid deleting these users by
migrating them to the new authentication source.  Your results may vary, and I
do not offer any guarantees so certainly test this procedure thoroughly if you
find yourself in a similar situation.

  * Backup the database before starting incase something goes wrong.
  * Lets assume the existing authentication source id = 201
  * Create a temporary authentication source used for migration.  Lets assume its id = 202. 
  * Configure both of these authentication source to point to the development Active Directory server.
  * Run the sync job only for auth source 202.
  * Run the following SQL script which generates another SQL script that will update the settings of users of the 201 auth source in the PTUSERS table to match those of the 202 auth source.
[sourcecode language='sql']SELECT 'UPDATE PTUSERS SET AUTHUNIQUENAME=''' +
AUTHUNIQUENAME + ''', DESCRIPTION=''' + DESCRIPTION + ''', AUTHUSERNAME=''' +
AUTHUSERNAME + ''' WHERE MAPPINGAUTHNAME=''' + MAPPINGAUTHNAME  ''' AND
AUTHSOURCEID=201;' FROM PTUSERS WHERE AUTHSOURCEID=202;[/sourcecode]

  * Verify the script that it generates escapes any apostrophe characters and then run it.
  * Run the following SQL script which generates another SQL script that will update the settings of groups of the 201 auth source in the PTUSERGROUPS table to match those of the 202 auth source. 
[sourcecode language='sql']SELECT 'UPDATE PTUSERGROUPS SET AUTHUNIQUENAME='''
+ AUTHUNIQUENAME + ''', DESCRIPTION=''' + DESCRIPTION + ''',
SYNCHGROUPNAME=''' + SYNCHGROUPNAME + ''' WHERE MAPPINGAUTHNAME=''' +
MAPPINGAUTHNAME + ''' AND AUTHSOURCEID=201;'  FROM PTUSERGROUPS WHERE
AUTHSOURCEID=202;[/sourcecode]

  * Verify the script that it generates escapes any apostrophe characters and then run it.
  * Delete the 202 auth source.
  * Run the 201 auth source sync job.
  * Verify that users you expected not to be deleted, were not deleted.
The PTUSERS table contains some CRC fields, which are based upon all of the
fields in a PTUSER record.  The easiest way to update these CRC values for a
user, is to save the user using the portal UI or API.  In the past I have
written a script that loops through each user in the authentication source and
saves them, thus updating the CRC fields, however I can not find it.  I will
leave this part as an exercise for the reader.  Just keep in mind that you
will need this before the user will be able to authenticate properly.
Although it does seem like the .NET portal relies on the CRC values more so
than the Java portal version.

As a side note, I am using the [SyntaxHighlighter
Plus](http://wordpress.org/extend/plugins/syntaxhighlighter-plus/) wordpress
plugin to provide the syntax highlighting.

