---
layout: post
title: "Brisbane .Net Meetup April 2015"
description: ""
date: 2015-04-21
category: 
tags: []
---

This month's [.Net  Meetup][1] was all the new things to see in Visual Studio 2015 and ALM 2015 - [Adam Cogan][2]

The talk covered a brief walk down memory lane including screenshots of each of the versions of Visual Studio since 2002.  Quite amazing to see exactly how much has changed.  No real discussion on how stability has greatly improved but some highly amusing discussions regarding the dreaded ALL CAPS MENUS![1i].

There was a brief look at the impressive [App Insights][4] which sadly doesn't have an easy binding for WinForms meaning it may be some time before I'll get to use it.

Great relaxed atmosphere as usual and while the talk pointed out a few things that aren't quite going to make it into the initial release we only covered half the topics.  I'll be looking forward to next month and ASP.Net + .NET Core changes (provided son 1.0 doesn't require my supervision).

I'll also try and remember to thank [Paul][5] or someone from [Octopus][6] as the free pizza is a life saver after missing lunch.

### PSA
Removing all caps can be achived by posting the following in Powershell or follow the original instructions on [stackoverflow][3].

#### VS2012

    Set-ItemProperty -Path HKCU:\Software\Microsoft\VisualStudio\11.0\General -Name SuppressUppercaseConversion -Type DWord -Value 1

#### VS2013
    Set-ItemProperty -Path HKCU:\Software\Microsoft\VisualStudio\12.0\General -Name SuppressUppercaseConversion -Type DWord -Value 1
	
There's also a menu option in VS2013 Update 3 if you've updated already.

[1]: http://www.meetup.com/Brisbane-Net-User-Group/events/221696495/
[2]: http://www.adamcogan.com/
[3]: http://stackoverflow.com/a/10859562
[4]: http://azure.microsoft.com/en-us/documentation/articles/app-insights-windows-usage/
[5]: http://paulstovell.com/
[6]: http://octopusdeploy.com/
[1i]: /assets/201504/201504_01_ALLCAPS.png