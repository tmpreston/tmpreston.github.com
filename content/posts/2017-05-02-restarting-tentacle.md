---
layout: post
title: "Restarting Tentacle"
description: ""
date: 2017-05-02
category: 
tags: [octopus]
---

Short post this time.  I was reviewing the newsletter for [Ocotopus Deploy][1] and came across an article on [automatically restarting Octopus Tentacle services][2].

I liked the idea but as part of my ***automate all the things*** preference at the moment I thought it should be possible to do this without getting an GUI involved.  Fortunately this is easily possible.  Start a console/cmd session with suitable Administrator rights and type the following:

    sc failure "OctopusDeploy Tentacle" reset=0 actions= restart/0/restart/0/restart/0

This happily set the first / second / subsequent failure actions.
![1i] 

    sc config "OctopusDeploy Tentacle" start= delayed-auto

To set the startup to 'Automatic (Delayed Start)'
![2i]

Hopefully this helps someone and/or makes me internet famous if it hits the [Octopus Deploy][1] newsletter!  I might even check how hard it is to use the Ocotopus [script console][3] to run it.

***Update***

Script console worked well.  Just used the following powershell to update a bunch of tentacles.

```Powershell
#Enable automatic recovery of *Tentacle* services
$TentaclesServices = Get-Service | Where-Object {$_.name -like '*Tentacle*'}
foreach($Tentacle in $TentaclesServices) {
    Write-Host Update serivce options for : $Tentacle.Name
    Write-Host `tDelayed start...
    sc.exe config $Tentacle.Name start= delayed-auto
    Write-Host `tRecovery options...
    sc.exe failure $Tentacle.Name reset=0 actions= restart/0/restart/0/restart/0
    Write-Host 'Complete'
}
```

[1]: https://octopus.com/
[2]: https://thaddparker.wordpress.com/2017/04/04/how-to-update-octopus-deploy-tentacle-to-restart-automatically/?__s=kv5pr8errbcsurcyn9np
[3]: https://octopus.com/docs/administration/script-console

[1i]: /assets/201705/0001_scfailure.png
[2i]: /assets/201705/0002_scconfig.png
