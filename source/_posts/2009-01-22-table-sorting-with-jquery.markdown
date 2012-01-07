---
author: kenan
date: '2009-01-22 19:57:06'
layout: post
comments: true
slug: table-sorting-with-jquery
status: publish
title: Table Sorting with JQuery
wordpress_id: '88'
categories:
- development
---

A very common request for HTML tables is making them sortable.  The
requirement came up the other day and I used [JQuery](http://jquery.com) and
the [JQuery Plugin tablesorter](http://tablesorter.com).  JQuery is a
excellent lightweight javascript library that is useful for all things
javascript.  It also allows its large developer community to develop plugins
such as the tablesorter plugin.  To use this in your web application, insert
the lines below and you are all set.  It does not get much easier than that,
plus it is really fast, has customization options, and just plain works.

    
    <script type="text/javascript" src="/path/to/jquery-latest.js"></script>
    <script type="text/javascript" src="/path/to/jquery.tablesorter.js"></script>
    
    [sourcecode language='javascript']$(document).ready(function()
        {
            $("#myTable").tablesorter();
        }
    );[/sourcecode]

One requirement is that the HTML table must use the THEAD and TBODY tags.  A
.NET GridView does not include these tags by default, but they can be added
easily enough with the following:

[sourcecode language='c#'] if (this.gridView.Rows.Count > 0) {
gridView.UseAccessibleHeader = true; gridView.HeaderRow.TableSection =
TableRowSection.TableHeader; } [/sourcecode]

