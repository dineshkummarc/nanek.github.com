---
layout: post
title: "Now using Octopress"
date: 2012-01-06 16:18
comments: true
categories: 
---

Nothing like migrating to a new blogging platform to get you in the mood
to write some new posts. Just switched from Wordpress to
[Octopress](http://octopress.org).

You can find migration instructions a number of places, but the process was pretty straightforward for me.

- Exported published posts from Wordpress
- Updated xml export to include atom namespace that was missing
- Used [exitwp](https://github.com/thomasf/exitwp) to convert the export
  into the markdown format. I did run into a [wrapping issue](https://github.com/thomasf/exitwp/issues/6).
- Enabled comments on old posts with the following find and replace

```
 perl -pi -e 's/layout: post/layout: post\ncomments: true/g' *.markdown
```

- Saved images to source/images and updated posts with proper links
- Deploy to github!
- Update feedburner RSS feed location

Now I just need to find a spell checker plugin!
