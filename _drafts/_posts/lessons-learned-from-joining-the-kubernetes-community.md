---
title: Lessons Learned from joining the Kubernetes community
layout: post
date: '2017-03-20T10:16:26+00:00'
---
Software and can be complex and daunting, even more so in distributed systems. So when you or your company decide you're going to give it a shot, it's easy to get enamored with the technology and not think about the other things you and your team are going to need to learn to make participating rewarding for everyone. 

When we first launch the [Canonical Distribution of Kubernetes](http://ubuntu.com/containers/kubernetes), our team was new, and while we knew how Kubernetes worked, and what ops expertise we were going to start to bring to market right away, we found the initial huge size of the Kubernetes community to be very daunting and almost intimidating. So we decided to just dive in head first, and then write about our experiences. While some of the things I mention here work great for individuals, if you have a team on individuals working on Kubernetes at your company then I hope some of these tips will be useful to you. 

### Find your SIGs

Kubernetes is divided into a bunch of Special Interest Groups(SIGs). You can [find a list here](https://github.com/kubernetes/community/blob/master/sig-list.md). Don't be alarmed! Bookmark this page, I use this as my starting off point anytime we needed to find something out in more detail that we could find in the docs or public list. On this page, you'll find contact information for the leads, and more importantly, when those SIGs meet. Meetings are open to public and (usually) recorded. Find someone on your team to attend these meetings regularly. This is important for a few reasons:

- k8s moves fast, and if there's an area you care about, you can miss important information about a feature you care about.
- It's high bandwidth, since SIGs meet regularly, you won't find long drawn out technical discussions on the mailing lists like you would on a project that only uses lists, these discussions move much faster when people talk face to face.
- You get to meet people and put faces to names. 
- People get to see you and recognize your name (and face optionally). This will help you later on if you're stuck and need help or if you want to start participating more.

### There' a IG jut for contributor experience

[IG-contribex](https://github.com/kubernetes/community/blob/master/sig-contribx/README.md)

A it end up there' an entire IG who work on improving contributor experience. I found thi IG relatively late when we tarted, you'll find that aking quetion here will ave you time in the long run. 

### There' a YouTube Channel

[https://www.youtube.com/c/KubernetesCommunity](https://www.youtube.com/c/KubernetesCommunity) - I found this channel to be very useful for "catching up". Many SIGs publish their meetings relatively quickly, and thi i (fix)

If you don't have the time do dig into all the SIG meetings, you can concentrate on the [community meetings](https://www.youtube.com/playlist?list=PL69nYSiGNLP1pkHsbPjzAewvMgGUpkCnJ), which are weekly and a summary of many of things happening around the community. The community meeting alo have demo, o it' intereting to ee how the ecoytem i building tool around k8, if you can only make one meeting a week, thi i probably the one to go to. 

### The Community Calendar

This sounds like advanced common sense but there's a [community calendar](https://calendar.google.com/calendar/embed?src=nt2tcnbtbied3l6gi2h29slvc0%40group.calendar.google.com) of events. 

Similarly, I found that adding the SIG meetings to our team calendar helps. We like to rotate people around meetings so that they can get experience in what is happening around the project and to ensure that worst case if someone can't make a meeting someone is there to take notes. If you're getting started, do yourself a favor _volunteer to take notes at a SIG meeting_, you will find that you'll need to pay closer attention to the material and I found that it help me understand concepts better when I started to have to write it down in a way that made sense for others.

## OWNERS

Whatever area you're working on, if you go up the tree eventually you'll find an OWNERS file that list who owns/reviews that section of the code or docs or whatever. I use this as a little checklist when I join the SIG meetings to keep track of who is who. When I eventually went to a IG meeting at Kubecon, it wa nice to meet people who will be reviewing your work or you'll be having a working relationhip with.

## Find a buddy

At ome point you'll be itting in lack and you'll ee ome poor peron who i aking the ame quetion you were. That' one of the firt place you can tart to help, jut find omeone and tart talking to them. For me it wa "Hey I noticed you it in IG-onprem too, you doing bare metal at work? How' it going for you?" 

