---
layout: post
title: "App store not friends with IPv6"
description: ""
date: 2017-11-25
category: 
tags: []
---
I recently had some issues trying to download a game [Shadows Of War][1] from the Microsoft Store.  Despite a number of google searches including reddit threads, official forums etc, there didn't seem to be any recommended solution/s (Some places suggested re-installing windows but I wasn't quite up for that).

I tried looking into task manager and then resource monitor and noticed that store application was making some IPv6 connections but no data was being transferred.  I disabled IPv6 and downloading started flawlessly.

![1i]

This may have just been co-incidence but maybe this post can help someone.

* Windows 10 / Version 1709 / OS Build 16299.19 *

[1]: https://www.microsoft.com/store/productId/9MW4TZ50746T
[1i]: /assets/201711/0001_ipv6.png
