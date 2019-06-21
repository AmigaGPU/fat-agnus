---
title: VoiceMeeeter HOWTo for streamers and SoHo studio's
published: false
description: How to use VoiceMeeeter mixing console for streamers & in SoHo studios
tags: #SoundEngineering #DAW #Alsa #Jack
---


## VoiceMeeeter HOWTo for streamers and SoHo studio's 
realtime synced(*)

VoiceMeeeter is a **professional** mixing console in software, runs in most win-x flavours.

Because it's a real mixer the connections you can make with it are as versatile as my real mixing consoles in the studio and at home.

The biggest console has a limit of **6hrs** of use, after which it _interrupts_ your audio briefly. **Banana** has a maximum of three hardware inputs, that is more than enough for the average streamer. It even is good enough for me in my SoHo studio, from which I also stream.

Users who need more than three hardware inputs can easily pay the authors via the donationware system that VoiceMeeeter has in place, you basically pay what you can afford.

Just like a real PA mixer needs a _snake_ to connect the stage audio equipment with the mixing console, VoiceMeeeter uses virtual audio cables, of which two can be used along with the **_Banana_** and **Potato** version of the mixer. The two others are also donation-ware.

**Virtual Audio Cable** is the first cable system.

**_HiFi_ Virtual Audio Cable** is the second cable system.

You tell your audio applications to send their output to one of the two snakes.

On your VoiceMeeeter Mixer you patch one of the multi-channel faders to **_HiFi_ Virtual Audio Cable** and another to **Virtual Audio Cable**

Check the screenshot here <https://imgur.com/wtSx56a>

I've mapped one audiosource to **kernel mode** _Virtual Cable_ (2nd hardware fader) and another audio source to **_HiFi_ Virtual Audio Cable** which I patched to the third hardware fader. The first fader has my **Behringer** the digitizer, which converts audio from my Yamaha mixing console to very low-latency HQ digital audio.  

Because these cables are in essence **audio snakes** you can connect as many audio sources as you want to them so the mixer fader then acts as a _group fader_ for all these sources.

A physical mixer has two or more subgroups where you assign the individual channels to a subgroup. These are _vital_ when you need to drop or raise the **whole brass** or woodwind  **section**, in relation to the rest of the mix, while saving their individual fader difference.

The same will be achieved with assigning audio outputs of different sources to the two snakes provided with VoiceMeeeter **Banana**. 

When the fader of **_HiFi_ Virtual Audio Cable** is pulled down, everything connected to it, drops with the ammount of dB that you requested. 

When the fader of **Virtual Audio Cable** is pushed up, everything connected to it, _increases_ with the ammount of dB that you requested.

In this manner you have the same control I have with my physical mixers. The big difference is with _latency_

My physical mixing consoles have one strong point you may lack with a software mixers like VoiceMeeter.

## Their latency is 0ms!

In VoiceMeeeter you have to work on minimizing latency by following the system requirements, or dropping the load on the mixer. If it has less to do, it will task your CPU at a lower rate. The stronger your #DAW is in CPU power, the _**lower**_ your **latency** will become once you tweak it.

I won't bother teaching you here _how_ to do it. That's not the scope of this HOWTO. There are excellent video's on youtube which explain this in meticulous detail.

Another strong point that _physical audio mixers_ have is **direct access** to the faders, no keyboard combo's or shortcuts or USB-interfaces mapped to the faders (the latter can also cause latency). Direct access to the faders makes all dynamic audio operations incl streaming very handy & transparent.

The VoiceMeeeter mixing console has its own strong points. Almost _limitless_ ammount of connections are possible through the **Virtual Audio Cable** system. Of course there are limits, which are imposed by your computer hardware but you are quite flexible to patch audio sources to the mixer.

Because you can also interface with VST-Realtime effects a whole world opens up for you. I have connected nice 'analog'(**) compressors, limiters & delays via a VST-host that I love, thus creating a full fledged mixing console with an FX-rack controlled via my VST-host. 

I've just run another session with my favourite VST host. Since I use it purely as an FX rack, only inputs and outputs are important for me to look at, apart from the dB levels of the audio streams. I have a few screenshots here <https://imgur.com/kzhUZTj>

As you can see I love using _analog_ type effects, esp when it comes down to compressors limiters and gates (which I use for mic's to cut unwanted background noise). 

When it comes down to noise I have a simple credo. A house should sound like a house, so there should be a *lot* of noises, even _**babies*_ crying are **normal** house noises. If I need a studio noise floor, I either go into one I own, or build a new one to the lower floor specs I need. The **lower** the noise floor the more expensive the physical structure & the damping sound attributes.

Finances should never be a limiting factor when it comes down to audio work. If you let money stop you _dead_ in your tracks you should **not** become a Sound-Engineer.

Countless times I've had mishaps in the field, from roadies plugging expensive equipment into the wrong power sockets (that ties you with us for a year or two to pay it off) to unexpected critical equipment failures.

The show always goes on, _**ON TIME**_ whatever the problems we've had.

## A few things are important.

I always tell the client that we come way before the event, to not only check out the venue, but also get a sense of the **acoustics**, the roads to and fro (so we know which truck{s}) can we use to haul the gear).

Sometimes we need to get licenced electricians to get the electrical power in the building balanced in a way we can safely work without getting a lack of Amperes when they are really needed. THat can take from days to weeks to get done, and of course the power company needs to clear the mods before we are allowed to work in the venue (again).

In some cases the amplifiers need to work hard briefly, to deliver peak program of the band, after which they drop to the normal RMS' levels again. When you have no exact sense of what the power-lines can deliver smoothly when your amps peak, you will be in for a **nasty** surprise when suddenly your dB's _drop_ to a level where the crowd overscreams the band and your PA.

Another important factor for road work is sleep. Yeah sleep: just like with truck drivers your crew needs to sleep enough, in order to work deep into the night as if it were daytime.

You are better of with **nocturnal** people, who just love to work when all other normals sleep. The others need to manage their sleep in a good manner.



(*)
This doc is synchronized via **github!** This is the link to the latest update in the repository
<https://github.com/AmigaGPU/fat-agnus/blob/master/voicemeeeter_mixers_small_howto.md>

(**)
_Analog_ in the sence that the effect has true VU-meter behaviour and a well executed behaviour pattern of its analog counterpart, like tube distorters and effects of that nature.

This HowTO is a *wip, work in progress* Its not finished yet. It is ripe for prelimenary publishing, which is the main reason why I released it.