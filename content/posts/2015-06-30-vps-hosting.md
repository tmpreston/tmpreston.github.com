---
layout: post
title: "VPS Hosting"
description: ""
date: 2015-06-30
category: 
tags: []
---

Before hosting here on the awesome [GitHub Pages][1], I contemplated setting up a VPS server.  One of my first choices, [Digital Ocean][2] recently sent me an offer for a free T-shirt if I set up a _droplet_ and answered some survey questions.  

I haven't gotten a free T-shirt since my initial take on [Xamarin][4], so I decided to see how hard it would be to setup [Jekyll][3] on a clean VPS.

Initial seutp was easy and the VPS control panel was clean and simple.
![1i]
![2i]

Getting the current blog up just required running a few commands: (and I didn't even need to look them up)

    apt-get install jekyll
    apt-get install git
    git clone https://github.com/tmpreston/tmpreston.github.com

Running jekyll using the inbuilt server (jekyll server --host=0.0.0.0) proved to be nice and speedy too.
![3i]

And just for completeness I tried [nginx][5] too.

    apt-get install nginx
    cp -R * /var/www/html/
	
The control panel has some basic in-built reporting already.  
![4i]
And a handy reset root password utility if you end up not pasting a valid SSH public key during _droplet_ creation.

Everything worked well and prior to destruction of my little _droplet_ I thought I'd check how fast the SSD disk was.

    hdparm -t /dev/vda
    hdparm -T /dev/vda

![5i]

So if ever [GitHub][6] does decide that they don't particularly want to be in the free hosting business I should be able to happily keep on blogging about my latest IT/Dev adventures.


[1]: https://pages.github.com/
[2]: https://www.digitalocean.com/?refcode=bb3d150415f0
[3]: http://jekyllrb.com/
[4]: http://xamarin.com/f-sharp-shirt
[5]: http://nginx.org/en/
[6]: https://www.github.com

[1i]: /assets/201506/01_droplet_creation.png
[2i]: /assets/201506/02_droplet_creation.png
[3i]: /assets/201506/03_droplet_jekyll_host.png
[4i]: /assets/201506/04_droplet_command_panel.png
[5i]: /assets/201506/05_hdd_stats.png