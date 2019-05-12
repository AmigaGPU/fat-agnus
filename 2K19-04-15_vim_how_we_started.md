---
title: VIM the beginning...
published: false
description: How I started out using vim part-I
tags: #vim #vi #programming #betatesting
---

I started with vi on noisy phone lines for the BBS systems of our university.

I was a student then, who had the task to punch holes in the system for the URC(*) director so he could fix them.

That was in the 1990's a century ago ;)

My vim use back then was as follows:

- `vim filename.extension`
- `:i`
- enter & correct data while:
- Regularly getting in & out of interactive mode the moment the line goes bad (**)
- do a `:u` in combo with `^L` when bad stuff came on the screen
- `:w` in between (I had to do this **very often** since `ATH0` was often send to the Telebit 9600bps modems when the lines went beserk)
- `:wq` at the end when all looked good on the screen.


The power of _insert mode_ saved my sanity on the copper wires from the **POTS** phone system, where I had to edit files over. THe analog POTS centrals of our phonecompany were run on wires, which were way too old, which means with rain, a lot of moisure creeps in the cable, forcing a lot of noise over the lines.

For a while this was the only way I used vi. I did not bother with learning others since this was all I needed.

After a while I wanted to see what I could do more with vi. However the man files for vi were not on the machines I used vi from. Then someone told me that **vim** by _Bram Molenaar_ had buildin help just like emacs, an editor I could not run due to the ram constraints my workstation had.

I downloaded vim on my m68k Amiga and loved the startup screen. It looked very similar to this one <https://imgur.com/QqMPp4Q>

The next screen is what made my decision final <https://imgur.com/POyJPHr>

THe fact that I could use vim with build-in help was an eyeopener. From then on I realized, I  can take my time and learn new stuff right in the editor.

### AMAZING!

That is how this discovery felt. Esp in a time when multi monitor setups at home were non-existent, since I wanted to be in the editor while I learn new stuff I need, for the tasks at hand.


Note: I will use the terms **vim** and _vi_ interchangeably. When I talk about the bare version, I reference POSIX vi which you should find on all posix compliant OS'es


(*)
The modems in that period had MNP5 & other protocols which were supposed to help against unstable phone lines. They were not prepared against the LQ lines we had in our country.

(**)
URC = Universitair Reken Centrum -> University Computer Lab


This document is a _w.i.p_ it's not finished yet. I publish it now since it's been in the pipeline for a while already & is already in **a readable state**

Direct link to the last synced version:
<https://github.com/AmigaGPU/fat-agnus/blob/master/2019-04-04-building-a-programming-env-in-2k19-3.md>
