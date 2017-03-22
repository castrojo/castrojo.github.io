---
title: Lessons Learned from joining the Kubernetes community
layout: post
date: '2017-03-20T10:16:26+00:00'
---


Software can be complex and daunting, even more so in distributed systems. So when you or your company decide you're going to give it a shot, it's easy to get enamored with the technology and not think about the other things you and your team are going to need to learn to make participating rewarding for everyone.

When we first launched the 
<a href="http://ubuntu.com/containers/kubernetes">Canonical Distribution of Kubernetes</a>, our team was new, and while we knew how Kubernetes worked, and what ops expertise we were going to start to bring to market right away, we found the initial huge size of the Kubernetes community to be ouright intimidating. Not the people of course, they're great, it's the learning curve that can really seem large. So we decided to just dive in head first, and then write about our experiences. While some of the things I mention here work great for individuals, if you have a team on individuals working on Kubernetes at your company then I hope some of these tips will be useful to you. This is by no means an exhaustive list, I'm still finding new things everyday.

### Find your SIGs

Kubernetes is divided into a bunch of Special Interest Groups(SIGs). You can 
<a href="https://github.com/kubernetes/community/blob/master/sig-list.md">find a list here</a>. Don't be alarmed! Bookmark this page, I use this as my starting off point anytime we needed to find something out in more detail that we could find in the docs or public list. On this page, you'll find contact information for the leads, and more importantly, when those SIGs meet. Meetings are open to public and (usually) recorded. Find someone on your team to attend these meetings regularly. This is important for a few reasons:
* k8s moves fast, and if there's an area you care about, you can miss important information about a feature you care about.
* It's high bandwidth since SIGs meet regularly, you won't find long drawn out technical discussions on the mailing lists like you would on a project that only uses lists, these discussions move much faster when people talk face to face.
* You get to meet people and put faces to names.
* People get to see you and recognize your name (and optionally, your face). This will help you later on if you're stuck and need help or if you want to start participating more.
* Each team has a slack channel and google group (mailing list), so I prefer to sit in those channels as well as they usually have important information announced there, meeting reminders, and links to the important documents for that SIG.

### There's a SIG just for contributor experience

<a href="https://github.com/kubernetes/community/blob/master/sig-contribx/README.md">SIG-contribex</a> - As it ends up there's an entire SIG who work on improving contributor experience. I found this SIG relatively late when we started, you'll find that asking quetions here will save you time in the long run. Even if you're not asking questions yourself you can learn about how the mechanics of project works just by listening in on the conversation.

### So many things in /community

<a href="https://github.com/kubernetes/community">https://github.com/kubernetes/community</a> - This should be one of your first starting points, if not the starting point. I put the SIGs above this because I've found for most people they're initially interested in one key area, and you can just go to that SIG directly first to get started then come back to this. That doesn't mean this isn't important, if I get lost in something this is usually the place I start to look for something. Try to get everyone on your team to have at least a working understanding of the concepts here, and of course don't forget the CLA and Code of Conduct.

### There's a YouTube Channel

<a href="https://www.youtube.com/c/KubernetesCommunity">https://www.youtube.com/c/KubernetesCommunity</a> - I found this channel to be very useful for "catching up". Many SIGs publish their meetings relatively quickly, and tossing in the channel in the background can help you keep track of what's going on.

If you don't have the time do dig into all the SIG meetings, you can concentrate on the 
<a href="https://www.youtube.com/playlist?list=PL69nYSiGNLP1pkHsbPjzAewvMgGUpkCnJ">weekly community meeting</a>, which is held weekly and a summary of many of things happening around the different SIGs. The community meetings also have demos, so it's intereting to ee how the ecosytem is building tools around k8s; if you can only make one meeting a week, this is probably the one to go to.

### The Community Calendar and meetings

This sounds like advanced common sense but there's a 
<a href="https://calendar.google.com/calendar/embed?src=nt2tcnbtbied3l6gi2h29slvc0%40group.calendar.google.com">community calendar</a> of events.

Additionally, I found that adding the SIG meetings to our team calendar helps. We like to rotate people around meetings so that they can get experience in what is happening around the project and to ensure that worst case if someone can't make a meeting someone is there to take notes. If you're getting started, do yourself a favor *volunteer to take notes at a SIG meeting*, you will find that you'll need to pay closer attention to the material and for me it helps me understand concepts better when I have to write it down in a way that makes sense for others.

We also found it useful to not flood one meeting with multiple people. If it's something important, sure, but if you just want to keep an eye on what's going on there you can only send one person and then have that person give people a summary at your team standup or whatever. There are so many meetings that you don't want to fall into the trap of having people sitting in meetings all day instead of getting things done.

## OWNERS

Whatever area you're working on, go up the tree and eventually you'll find an OWNERS file that list who owns/reviews that section of the code or docs or whatever. I use this as a little checklist when I join the SIG meetings to keep track of who is who. When I eventually went to a SIG meeting at Kubecon, it was nice to meet people who will be reviewing your work or you'll be having a working relationhip with.

## Find a buddy

At some point you'll be sitting in slack and you'll see some poor peron who is asking the same sorts of questions you were. That's one of the first places you can start to help, just find someone and start talking to them. For me it wa "Hey I noticed you sit in SIG-onprem too, you doing bare metal? How's it going for you?"

## It's too big!

This used to worry me because the project is so large I figured I would never understand the entire thing. That's ok. It's totally fine to not know every single thing that's going on, that's why people have these meetings and summaries in the first place, just concentrate on what's important to you and the rest will start to fall into place.

## But we only consume Kubernetes, why participate?

One of the biggest benefits of consuming an open source project is taking advantage of the open development process. At some point something you care about will be discussed in the community then you should take advantage of the economies of scale that having so many people working on something gives you. Even if you're only using k8s on a beautifully set up public cloud from a vendor where you don't have to worry about the gruesome details, your organization can still learn from all the work that is happening around the ecosystem. I learn about new tools and tips every single day, and even if your participation is "read-only", you'll find that there's value in sharing expertise with peers.

## Ongoing process

This post is already too long, so I'll just have to keep posting more as I keep learning more. If you've got any tips to share please leave a comment, or post and send me a link to link to.