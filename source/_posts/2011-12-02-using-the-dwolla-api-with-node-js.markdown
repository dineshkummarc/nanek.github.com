---
author: kenan
date: '2011-12-02 10:55:52'
layout: post
comments: true
slug: using-the-dwolla-api-with-node-js
status: publish
title: Using the Dwolla API with node.js
wordpress_id: '412'
categories:
- development
- payments
---

[Dwolla.com](http://dwolla.com) is a new payment network. It makes it easy to
transfer money without the transaction fees charged by credit cards. Each
transaction over $10 is 25 cents, and those under $10 are free. I think this
has a lot of potential so I have been exploring ways to utilize their API.

To start I wrote a node.js module for their API that you can find at
[https://github.com/nanek/node-dwolla](https://github.com/nanek/node-dwolla).
In addition, I added Dwolla OAuth2 to the
[everyauth](https://github.com/bnoguchi/everyauth) module to make it easy to
authenticate.

They have some interesting API methods that are not common to payment APIs.
You can view a user's account transactions and balances (with permission of
course). They also integrate and expose a user's contacts from various social
networks, such as Facebook and Twitter, to make it easy to send/request money
from friends.

Let me know if you build something cool or if you have a great idea that could
utilize their API.

