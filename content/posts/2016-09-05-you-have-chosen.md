---
layout: post
title: "You have chosen..."
description: ""
date: 2016-09-05
category: 
tags: []
---

![1i] 

It's been an interesting year at work.  I've been hard at work on creating a cloud based offering of our application.  This wasn't something on the roadmap as the application was a thick client built on .NET in WinForms.  Recently cloud providers have been trying to ensure that they're able to migrate any and all software and so we ended up investigating a [Azure RemoteApp][1].

RemoteApp allowed us to take an application built for LAN/WAN deployment and without needing to make huge changes provide a service with very low initial costs (no expensive servers, no windows licensing & no SQL licensing).  Having a Mac OS X, iOS and Android applications proved very popular.  The multiple options to accessing data (including the preview of the HTML5 client) was great and it's quite incredible seeing an application originally written in .NET 1.1 (and slowly migrated through the years) suddenly accessible on an iPhone.

But sometimes good things must come to and end and Microsoft is [shutting down RemoteApp][2].  There aren't many details available yet but hopefully the migration path proves easy to implement.  The existing processes to manage template images/collections (and even configuring drive redirection) weren't without issues,  (I had to switch from powershell to web API to workaround some quirks) but were definitely simpler than configuring/managing a complete desktop services environment (and having to come up with session management/tracking/pricing)

On the plus side, I do feel like I've finally managed a right of passage.

LINQ to SQL (dodged)
Silverlight (dodged)
Azure RemoteApp .... 

![2i]

[1i]: /assets/201609/0001_youhavechosenpoorly.jpg
[2i]: /assets/201609/0002_achievement.gif
[1]: https://azure.microsoft.com/en-us/services/remoteapp/
[2]: https://blogs.technet.microsoft.com/enterprisemobility/2016/08/12/application-remoting-and-the-cloud/
