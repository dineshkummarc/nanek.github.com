---
author: kenan
date: '2011-11-17 14:24:20'
layout: post
comments: true
slug: translation-api-for-node-js
status: publish
title: Translation API for node.js
wordpress_id: '407'
categories:
- development
---

Microsoft provides a Translator API that allows you to translate text from one
language into another. It provides up to 1000 transactions/month for free.
Google also provides a translation API, however has recently removed their
free tier. One the projects I am working on needed the ability to translate
text, so I wrote a node.js module for the Microsoft Translator API, which you
can find more about at
[github.com/nanek/mstranslator](https://github.com/nanek/mstranslator).

The API itself provides a good set of languages to choose from and it also can
provide the audio of the word being spoken.

