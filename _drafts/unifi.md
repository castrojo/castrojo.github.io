---
published: true
title: Unifi's new switches are great
layout: post
---

I started switching to Unifi equipment at home when one of my coworkers, Sean Sosik-Hamor, recommended them for prosumer use. A little while later Lee Hutchinson published [Ubiquiti Unifi made me realise how terrible consumer Wi-Fi gear is](http://arstechnica.com/gadgets/2015/10/review-ubiquiti-unifi-made-me-realize-how-terrible-consumer-wi-fi-gear-is/) when they launched their newer (and cheaper) line of 802.11ac access points. I've got one of those, as well as the [USG](https://www.ubnt.com/unifi-routing/usg/) for routing duties. The USG isn't something to write home about, but it gets the job done, and in some advanced cases you can always ssh to it, but generally speaking I just use it as intended and mostly setting it up and forgetting about it. 

![unifi](/images/unifi/unifi1/png)

Unlike most routers, you don't manage Unifi gear through a web UI on the device, you run controller software on a host and then the controller software blasts out the config and updates to the devices. I recommend reading Dustin Kirkland's [blog post for running Unifi in LXD](http://blog.dustinkirkland.com/2016/12/unifi-controller-in-lxd.html) as it currently is 14.04 only, and if you're like me, you're finding that it's becoming much more manageable to keep server software nice and isolated in it's own container instead of splatting all its dependencies on the host OS. 

