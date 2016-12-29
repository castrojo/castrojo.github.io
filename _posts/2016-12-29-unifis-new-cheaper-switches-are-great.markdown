---
published: true
title: Unifi's new cheaper switches are great
layout: post
---

I started switching to Ubiquiti's Unifi equipment at home when one of my coworkers, Sean Sosik-Hamor, recommended them for prosumer use. A little while later Lee Hutchinson published [Ubiquiti Unifi made me realise how terrible consumer Wi-Fi gear is](http://arstechnica.com/gadgets/2015/10/review-ubiquiti-unifi-made-me-realize-how-terrible-consumer-wi-fi-gear-is/) when they launched their newer (and cheaper) line of 802.11ac access points. I've got one of those, as well as the [USG](https://www.ubnt.com/unifi-routing/usg/) for routing duties. The USG isn't something to write home about, but it gets the job done, and in some advanced cases you can always ssh to it, but generally speaking I just use it as intended and mostly setting it up and forgetting about it. 

![unifi](/images/unifi/unifi1.png)

Unlike most routers, you don't manage Unifi gear through a web UI on the device, you run controller software on a host and then the controller software blasts out the config and updates to the devices. I recommend reading Dustin Kirkland's [blog post for running Unifi in LXD](http://blog.dustinkirkland.com/2016/12/unifi-controller-in-lxd.html) as it currently is 14.04 only, and if you're like me, you're finding that it's becoming much more manageable to keep server software nice and isolated in it's own container instead of splatting all its dependencies on the host OS. If you prefer things more old school, look for the "EdgeRouter" line of routers and switches. 

At $99 for an AP and $149 for an access point you can come up with a nice business-grade combo, especially with the latest consumer routers starting to get close the $300(!) and utterly terrible software. The one thing that was always expensive though, was the Unifi line of managed switches. It's nice, but at $199 for 8 ports, just too much for each port. Here's a nice review from Lee on the [Unifi Switch 8](http://arstechnica.com/gadgets/2016/04/ubiquitis-8-port-poe-switch-is-a-solid-complement-for-a-home-unifi-setup/). Thanks to the wonder of their beta store, I was able to pick up the newer, slimmed down 8 port, the Unifi US-8: 

![unifi8](/images/unifi/unifi8.jpg) 

There it is, with the unmanaged switch it replaced. They dropped the SFP ports, and you can see the port LEDs are on the top instead of in each port, probably for cost? And since it's Unifi, it plops in nicely with the UI, giving me some nice per-port stats:

![unifi3](/images/unifi/unifi3.png)

And it gets better, they've done a US-24 and US-48 as well. I put a US-24 in my basement. $215 all day for 24 ports, compared to the older model, which would go north of $500!  

![unifi2](/images/unifi/unifi2.png)

I'm in the process of still setting up the homelab VLAN, so I don't have much to report on that, but having everything managed in one system is a really great feature. I didn't really need SFP plugs or lots of PoE power for my use, so this new low-end line is perfect for me, if you find yourself wanting cheap-but-good equipment with decent software, then I recommend you check them out, and of course drop by [/r/ubiquiti](https://www.reddit.com/r/Ubiquiti/) if you need anything. 
