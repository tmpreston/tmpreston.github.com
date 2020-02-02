---
layout: post
title: "Life on the bleeding edge... bleeding"
description: ""
date: 2015-05-03
category: 
tags: []
---


![1i] 

### The start
Exciting times at the moment with the release of the RC for Visual Studio 2015 Community (& Enterprise Editions).  Since I'm normally technically curious I thought I'd [download][1] and have a look.  Obviously the first step I took was to run 

    vs_community.exe /layout

via the commandline to allow downloading the complete installer (in case I want to re-install it later).  A few hours later in the morning before work I decided to kick off the install only to find out I did not have the required **25GB** free space on my aging 120GB SSD.

### The unnecessary but totally justifiable shopping trip...
My free space problem was easily solved by a short trip to [Umart][2] to purchase a shiny new [Crucial MX100 256GB SSD][3a] 

![3b]

The next goal was to relocate my windows 8.1 installation from the old SSD to the new one.  My attempts to do this using the provided Acronis True Image software was unsuccessful and I didn't have any luck with EaseUS Partition Master either.  Third time lucky with [Clonezilla][4] which I turned to rather the resorting to a linux live cd and looking up the unfamiliar commandline arguments required. (I used the awesome [Rufus][5] to create a bootable USB stick because really who has a CD/DVD drive on their computer these days).

Finally with some free space. ![2i] 

I completed my initial goal: Install Visual Studio 2015 Community.

![3i]

### Scope creep

 
>Technology... is a queer thing. It brings you great gifts with one hand, and it stabs you in the back with the other.
><cite>Carrie Snow</cite>

At this point most people would bask in the glory of their technical achievement and fire up VS to see what's new.  I however saw my now unused SSD and thought you know I could probably install the new [Windows 10 Preview][6] build that was released today too.  Some downloading and some creating bootable USB sticks later and I've got a nice dual boot system.  Windows 10 has some big changes (the re-designed start menu really stands out) but otherwise is much more evolutionary.  The UI is subtly different but will be very familiar to anyone who has used Windows 8/8.1.

My foray into Windows 10 was short lived however.  Either the nvidia drivers, one of the windows updates available or possibly switching to the fast ring updates rendered my machine unbootable after the required restart.   Windows would start (bypassing all attempts to enter safe mode via F8) but end up on a black screen with a responsive mouse cursor.

Turning once again to my bootable USB stick I attempted to run windows recovery.  This automated process has saved my install/s in the past so I was happy to give it a try.  So now my original Windows 8.1 install is no longer available in the boot screen and the machine is still unbootable :(

![4i]

Using the USB to enter the console and force a safe mode start up allowed me to create a Windows 8 USB stick to repair the original install.  Some hours later and I've recovered my original windows installation.  At this point I've decided maybe I'll just use my old SSD for some games / programming projects. (At least untill the next major Windows 10 release is available.  RC can't be that far away).

### Quitting while I'm ahead
So for now I'll look into some of the new shininess that VS 2015 brings to windows.  I've got a draft post about [Telerik AppBuilder][7] so I'll maybe finish that off next and then compare it to the new [Cordova][8] support now available through VS 2015.

[1i]: /assets/201505/03_01_DownloadAvailable.png
[2i]: /assets/201505/03_03_Free_at_last.png
[3i]: /assets/201505/03_04_Installing.png
[4i]: /assets/201505/03_05_Bleeding.png
[1]: http://go.microsoft.com/fwlink/?LinkId=524433
[2]: http://www.umart.com.au 
[3a]: http://www.amazon.com/gp/product/B00KFAGCWK/ref=as_li_tl?ie=UTF8&camp=1789&creative=9325&creativeASIN=B00KFAGCWK&linkCode=as2&tag=tmprestonblog-20&linkId=GPLYJEQRJPZ7D6AI
[3b]: /assets/201505/03_02_MX100SSD.jpg
[4]: http://clonezilla.org/downloads/download.php?branch=alternative
[5]: https://rufus.akeo.ie/
[6]: http://windows.microsoft.com/en-au/windows/preview-iso
[7]: http://www.telerik.com/appbuilder
[8]: http://cordova.apache.org/