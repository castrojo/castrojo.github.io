---
layout: post
title: "70k Nvidia Downloads in 6 months"
categories: [ubuntu]
---

It’s been about six months since ricotz and mamarley have [brought fresh
Nvidia
drivers](http://www.omgubuntu.co.uk/2015/08/ubuntu-nvidia-graphics-drivers-ppa-is-ready-for-action)
to Ubuntu users. I covered some of this in my SCaLE 14x talk on [Ubuntu
Gaming](https://www.socallinuxexpo.org/scale/14x/presentations/gaming-ubuntu).
If you missed SCaLE then feel free to check out [Liz’s
summary](http://princessleia.com/journal/?p=11266).

In that talk I summarized some of the challenges (and victories!) to
making our platform be better for gamers. One of the obvious pain points
is of course, delivering fresh drivers for people, which can be
difficult (especially when it comes to managing regressions). First
let’s look at the version breakdown:

    346.72: 57
    346.96: 292
    352.21: 219
    352.79: 62
    355.06: 3291
    355.11: 11483
    358.09: 16949
    358.16: 22317
    361.18: 4076
    361.28: 10219

And then by Ubuntu release:

    precise: 630
    trusty: 30665
    vivid: 10908
    wily: 21537
    xenial: 5225

Trusty wins, no surprise there. Wow, way more people on Xenial than I
expected, good to see people are testing our upcoming LTS! And finally,
by architecture:

    amd64: 65661
    armhf: 31
    i386: 3273

So when you add them all up, it’s about 70,000 downloads of Nvidia
drivers from the PPA in the last six months. This is great, as it means
there’s certainly a demand for fresh drivers, but it’s also frightening
when you consider the end-user experience of traditional packaging and
all the wonderful face punching that entails. But hey, that’s XCOM.
Snappy can’t come fast enough!

Want to help? [Buy a game](http://store.steampowered.com/browse/linux/)
and check out
[ppa:graphics-drivers](https://launchpad.net/~graphics-drivers/+archive/ubuntu/ppa).

Oh and happy belated Vulkan day!
