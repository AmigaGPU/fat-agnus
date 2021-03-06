---
title: Building a programming ENV: in 2K19 III
published: false
description: How I build my programming ENV's on whatever machine I am the longest on part-III
tags: #golang #programming #linux #DAW
---

(*)Advanced Revision tracking via **git**

You know what the most important thing is when you make programming ENVs?

#### Consistency in workflow...

I want git to behave _almost_ the same in #linux #win64 and #freeBSD. Luckily the coders of git (which is the brainchild of Linus Torvalds) made sure of that. All that you need to do is use _bash_ that came with it, for the easiest path to that achievement. When you dig a bit into the subject, you will see that some clever translations are done for drive paths and such, so that they become consistent in linux and win64

The syntax is _/driveletter/path/to/dest_
So `/e/var/home/programmer/coding/linux/xplatfor/fat-agnus` would be a valid path in bash win64 and bash linux, while the underlying win64 filesystem (ntfs) letter and backslashes are translated to posix compliant equivalents, making the compilation of your sources easier, since you don't need to do any filesystem path conversions, by including an extra library for that function. Neat! 

Another beautiful thing about tools is that even though, they can do a **lot** you only need to learn what _you_ need, to achieve your goals.

I know no person who knows everything there is about bash, chances are that only the original programmers and contributors do, and that is a _group_ of people, a collective.

I do know one person who know a _lot_ about different shells, but that is simply because she *had to* gain that knowledge, due to her programming ENV: and workflow both in private and in her job

If you want to learn what she shared, I will link to that thorough body of work, at the end of this doc with (*)

Remember this:
<https://gnu.org> has all the doc info you need on bash

I have a number of examples in tweets which I shall just point you to.


This doc is new & considered _**w.i.p**_.

I will make a note when the doc is considered worthy for full publication.


(*)
Serious shell programming an **excellent course** by @freebsdfrau 
<https://freebsdfrau.gitbooks.io/serious-shell-programming/>


  #301daysofcode #100DaysOfCode #Linux #advancedprogramming hashtags on twitter

A fully synced update of this post resides here <https://github.com/AmigaGPU/fat-agnus/blob/master/2019-04-04-building-a-programming-env-in-2k19-3.md>

The other docs are also in that master branch


This is part-III of the series in which I will publish this thread.
