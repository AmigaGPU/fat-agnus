---
title: Building a programming ENV: in 2K19 II
published: false
description: How I build my programming ENV's on whatever machine I am the longest on part II
tags: #programming #golang #linux #DAW
---

(*)Revision tracking via **git**. This is how text editing should be controlled


As I said the last time having a smooth programming **ENV:** is important when you want to program on whatever machine (on your network) you are on.

The reason is obvious. I want to be able to code in between work / simulation / play & stream sessions. Even tiny snips of 15mins to 30 mins are benificial to me.

One annoying _problem_ of different cloud techs is that they want CC-info (think breaches), so I dont want that data spread everywhere) yet I have to learn 2 play with them somehow, at least those which give you a chance to.

#IBMCloud seems to play nice since they tell you what you can do on their network.

It may in the end be like the student licence from _ACAD_ but that one has the following benefits:

- fully functional systems
- you may download everything, save all files
- literally the whole software suit at your disposal for three years, so you can study everything
- the only catch is printing, that will show that you used a student licence, which is quite fine, since you **can work** with the program suite

### AWS

With open-source cloud techs like **#AWS** you are not allowed to fully test their stuff. Those guys want CC info.

Amazon has the following benefits:

- fairly good CC info protection
- you probably buy stuff there already so you have a card entered there also
- large network, lots of redundancy (good tech support?)


### The downside for users like me

1. impossible to test, for some reason it fails for me to activate #AWS
2. _**No testrun**_ of all means no way of learning how to use the cloudtech there.
3. opensource software effectively locked away behind a commercial veil.
4. Annoyance rises everytime I want to test it out ;)

I can run a free fully functional bash in a browser 
<https://console.cloud.google.com/cloudshell> at google

I did not know that it was in fact a free #docker container at my disposal.
#### Finally I can run some cloud tech in some capacity
## A full blown docker container!

As you can imagine I am seriously making time to play with this, since I don't need to run the server side for it (I dont have a free headless linux server anymore)


Notes:
(*)I love how it's now a breeze to keep the revisions of my markdown files in check.

All I need to do is enter `$ git commit -a`

Then I uncomment the line(s) with the revised file(s).

After a while I type:

$ `git status`

to see how many commits my branch is ahead. Then I can commence with `$ git push` to sync it all up with git.
Sweet and oh so neat ;)


This doc is now considered _**completed**_. I shall move to the next one now.

  #301daysofcode #100DaysOfCode #Linux #advancedprogramming hashtags on twitter

A fully synced update of this post resides here <https://github.com/AmigaGPU/fat-agnus/blob/master/2019-04-04-building-a-programming-env-in-2k19-ii.md>


This is part-II of the series in which I will publish this thread