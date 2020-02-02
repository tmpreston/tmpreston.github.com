---
layout: post
title: "Reading >> Listening"
description: ""
date: 2015-11-10
category: 
tags: []
---

#Excuses
I haven't had nearly as much free time recently due to the feature creep of son 1.0
![1i]

Time well spent however I haven't been spending much time **doing** which was my main goal for the year.  I've kept up with the usual blogs and tech news ( and decided I should really find a way to make the crazy amount of cash required to purchase a [Surface Book][1]).

#Doing
For quite a while I've been hoping to do some experiments/side projects exploring [Akka.NET][2].  There was an interview with one of the creators on [Hansel Minutes 472][3].  I don't have headphones for the train (the one reliable block of free time I have) so I've been patiently waiting for the transcription to be made available.  Six months patient even.  

Then fortuitously I managed to find a block of free time while at home.  Yes I could have listened to the mp3 version.  But instead what I did was think : How hard can it be to transcribe the audio myself so that next time there's an awesome podcast without a transcription I have some kind of solution.

And so was born: [BingVoiceTranscription][myg1]!

A jury-rigged system comprising of [Microsoft's Azure Bing Speech Recognition][4] and [NAudio][5].  No GUI (or even console input yet), just a simple program using XUnit tests to execute/drive it.

NAudio is used to convert the mp3 -> wav.  It's also used to split the wav data into 10 second chunks (the maximum allowed by Bing Voice).

The chunks of wav audio are then passed to the Bing webservice with the returned text being concatenated together.

The output is an impressive wall of text:

>Hey rock at a time for Ndc Oslos again June 15th through 19th in Oslo Norway Richard and I will be there of course.As well as all your favourite speakers world class stuff your folks in DC -oslo.com will see youthere.net rocks app.Srod 1134 with guest Erin Spattered recorded Friday April 10th 2015.Banner off Hey Richard Buddy are you doing I'm you know hanging along here by the years gone by really fast am again.Into the crazy conferences and so on what a good conference season It's gonna be is not so many things happening at once I'm judino I'm gonna have to end of juggling shows around.Is there gonna be a legitimate answer to stop at things coming to play yeah Yeah yeah well How do I load ka go first it's crazy that's true well and some things we can talk about that?What's even crazier yeah Not that I feeling like now we're gonna start having shows in the can that I can't even put on the schedule until were allowed to talk about on out with come out.Just say it's gonna be a goodyearfor.net developers It's been so much fun Yeah Alright Alright man Let's roll The music for better know framework awesome dude.Are you Would you got Well I would looking for some good current articles amtda I found one?It isn't directly related to akka.net or even the actor model but you know a lot of um games are programs with the actor model it makes.Lot of sense chair yet and so I found a great series of articles on codeproject.com about Unity 3D ok.This from April 4th filter in her Yep 5 stars 62 votes and the average is 4.96.Is people love this article is from Vahe Karamian and I'm sorry bye have fun miss pronounce your name but um because I'm stupid like I from Connecticut.But seriously I this is a great article I started a reading it in your I didn't go to the walk through But if you go to tiny url.Dot com slash unity walkthrough What unity ... (there's more but you get the idea).
	
It's kind of incredible some of the things that can be done in an hour or two of hacking these days.  The text isn't quite good enough so I may just need to listen to the podcast anyway but I'm curious what a bit more effort could do.  A few things come to mind already:

* detecting silence before splitting the file in to chunks
* using long pauses to create new paragraphs
* trying to train/feed some hints to Bing voice recognition (especially if I know what the mp3 source is about)

Creating transcripts from audio recently came up in a Xamarin application being developed at work so maybe I'll get to it sooner (and while on the clock).



[1]: https://www.microsoft.com/surface/en-au/devices/surface-book
[2]: http://getakka.net/
[3]: http://hanselminutes.com/472/inside-the-akkanet-open-source-project-and-the-actor-model-with-aaron-stannard
[4]: https://datamarket.azure.com/dataset/bing/speechrecognition
[5]: https://naudio.codeplex.com/

[myg1]: https://github.com/tmpreston/BingVoiceTranscription

[1i]: /assets/201511/01_SON10.png
