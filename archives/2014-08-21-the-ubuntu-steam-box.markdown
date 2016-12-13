<div class="container">

<div class="left-col">

<div class="intrude-less">

<div class="profilepic">

</div>

[Jorge's Stompbox](/)
=====================

Plug in, crank it to Eleven.
----------------------------

-   [About Jorge](http://about.me/jorge.castro)
-   [Bio](http://www.jorgecastro.org/about.html)
-   [Blog](/)
-   [Archives](/blog/archives)
-   [Public Key](https://keybase.io/castrojo/key.asc)
-   [My Wife, Jill](http://drjillcastro.org/)
-   [My Dog, Oscar](http://packdog.com/oscar-castro)
-   

\
### Projects I work on

-   [Ubuntu Server](http://ubuntu.com/server)
-   [Juju](http://juju.ubuntu.com)
-   [Juju Charms](http://jujucharms.com)
-   [Ask Ubuntu](http://askubuntu.com/users/235/jorge-castro)

\
### Projects that inspire me

-   [OpenStack](http://openstack.org)
-   [Discourse](http://discourse.org)
-   [FIRST Robotics Competition](http://usfirst.org)
-   [Little Kids Rock](http://www.littlekidsrock.org)

<div class="section aboutme">

I work on the Juju Ecosystem Team at Canonical Ltd. on Ubuntu Cloud and
Server, find me at jorge at ubuntu dot com.

</div>

<div class="social">

[Google+](https://plus.google.com/116015965439782966698 "Google+"){.google}
[Twitter](http://twitter.com/castrojo "Twitter"){.twitter}
[GitHub](https://github.com/castrojo "GitHub"){.github}
[](http://askubuntu.com/users/235/jorge-castro "Ask Ubuntu"){.stackoverflow}
[RSS](/atom.xml "RSS"){.rss}

</div>

</div>

</div>

<div class="mid-col">

<div id="banner" class="inner">

<div class="container">

</div>

[castrojo](http://twitter.com/castrojo) @ [Twitter](http://twitter.com)
<div class="loading">

Loading...

</div>

</div>

<div class="mid-col-container">

<div id="content" class="inner">

<div class="entry-content" itemprop="articleBody">

It’s been about a year since [I started building my own Steam
console](http://www.jorgecastro.org/2013/09/25/the-faux-steam-machine/)
for my living room. A ton has changed since then. SteamOS has been
released, In Home Streaming is out of beta and generally speaking the
living room experience has gotten a ton better.

This blog post will be a summary of what’s changed in the past year, in
the hopes that it will help someone who might be interested in building
their own “next-gen console” for about the same price, and take
advantage of nicer hardware and all the things that PC gaming has to
offer.

-   My [first blog
    post](http://www.jorgecastro.org/2013/09/25/the-faux-steam-machine)
    on building your own box.
-   A talk I gave at Penguicon on
    [SteamOS](https://www.youtube.com/watch?v=lXF5VebhhAc)
    for background.

Step 1: Choosing the hardware
-----------------------------

-   I consider the [NVIDIA GTX
    750Ti](https://www.youtube.com/watch?v=zcrFzOpTHkw) to be the best
    thing to happen in hardware for this sort of project. It’s based on
    their newest Maxwell technology so it runs cool, it does not need a
    special power supply plug, and it’s pretty small. It’s also between
    \$120-\$150 – which means nearly any computer is now capable of
    becoming a game console. And a competent one at that.

-   I have settled on the Cooler Master 110 case, which is one of the
    least obnoxious PC case you can find that won’t look too bad in the
    living room. Unfortunately Valve’s [slick-looking
    case](http://www.washingtonpost.com/blogs/the-switch/files/2013/11/med_STEAM_M_console__hero.jpg)
    did not kick the case makers into making awesome-looking living room
    style cases. The closest you can find is the [Silverstone
    RVZ01](http://www.silverstonetek.com/raven/products/index.php?model=RVZ01),
    which has the right insides, but they ruined the outside with crazy
    plastic ribs. The [Digital Storm Bolt
    II](http://www.pcworld.com/article/2465160/digital-storm-bolt-ii-review-rise-of-the-un-steam-machines.html)
    looks great, but you can’t buy the case seperately. Both cases have
    CD drives for some reason, boo!

![](http://www.jorgecastro.org/images/coolermaster.jpg)

-   Nvidia has a [great
    guide](http://www.geforce.com/whats-new/guides/geforce-gtx-750-ti-mini-itx-pc-build-guide)
    on building a PC within the console-price range if you want to
    look around. I also recommend checking out
    [r/buildapc](http://www.reddit.com/r/buildapc), which has tons of
    Mini-ITX/750Ti builds.

-   Another alternative is the excellent [Intel
    NUC](http://www.intel.com/content/www/us/en/nuc/overview.html) and
    [Gigabyte
    Brix](http://www.gigabyte.us/products/list.aspx?s=47&ck=104). These
    make for great portable machines, but for the upcoming AAA titles
    for Linux like Metro Redux, Star Citizen, and so on I decided to go
    with a dedicated graphics card. Gigabyte makes a [very
    interesting](http://www.gigabyte.us/products/list.aspx?s=47&ck=104)
    model that is the size of a NUC, but with a GTX 760(!). This looks
    to be ideal, but unfortunately when [Linus reviewed
    it](https://www.youtube.com/watch?v=hGI8iYjk0rc) he found
    heat/throttling issues. When they make a Maxwell based one of these
    it will likely be awesome.

-   Don’t forget [the
    controller](http://smile.amazon.com/Microsoft-Xbox-Wireless-Controller-Windows/dp/B004QRKWKQ/ref=sr_1_3?ie=UTF8&qid=1408660327&sr=8-3&keywords=xbox+controller+for+PC).
    The Xbox wireless ones will work out of the box. I recommend
    avoiding the off-brand dongles you see on Amazon, they can be hit
    or miss.

Step 2: Choosing the software
-----------------------------

I’ve been using SteamOS since it came out. The genious about SteamOS is
that fundamentally it does only 2 things. It boots, and then runs Steam
Big Picture (BPM) mode. This means for a dedicated console, the OS is
really not important. I have 2 drives in the box, one with SteamOS, and
one with Ubuntu running BPM. After running both I prefer Ubuntu/Steam to
SteamOS:

-   Faster boot (Upstart v. SysV)
-   PPAs enable fresh access to new Nvidia drivers and Plex Home Theater
-   Newer kernels and access to HWE kernels over the next 5 years

I tend to alternate between the two, but since I am more familiar with
Ubuntu it makes it easier to use for, so the rest of this post will
cover how to build a dedicated Steam Box using Ubuntu.

This isn’t to say SteamOS is bad, in fact, setting it up is actually
easier than doing the next few steps; remember that the entire point is
to not care about the OS underneath, and get you into Steam. So build
whatever is most comfortable for you!

![](http://www.jorgecastro.org/images/stats.jpg)

Step 3: Installation
--------------------

These are the steps I am currently doing. It’s not for beginners, you
should be comfortable admining an Ubuntu system.

-   Install Ubuntu 14.04.
-   (Optional) - Install `openssh-server`. I don’t know about you but
    lugging a keyboard/mouse back and forth to my living room is not my
    idea of a good time. I prefer to sit on the couch, and ssh into the
    box from my laptop.
-   Add the [xorg-edgers
    PPA](https://launchpad.net/~xorg-edgers/+archive/ubuntu/ppa). You
    don’t need this per se, but let’s go all in!
-   Install the latest Nvidia drivers: As of this
    writing, nvidia-graphics-drivers-343.

After you’ve installed the drivers and all the security updates you
should reboot to get to your nice new clean desktop system. Now it’s
time to make it a console:

-   Log in, and install Steam. Log into steam, make sure it works.
-   Add the Marc Deslaurier’s [SteamOS
    packages](https://launchpad.net/~mdeslaur/+archive/ubuntu/steamos) PPA.
    These are rebuilt for Ubuntu and he does a great job keeping them up
    to date.
-   `sudo apt-get install steamos-compositor steamos-modeswitch-inhibitor steamos-xpad-dkms`
-   Log out, and in the login screen, click on the Ubuntu symbol by the
    username and select the Steam session. This will get you the
    dedicated Steam session. Make sure that works. Exit out of that and
    now let’s make it so we can boot into that new session by default
-   [Enable autologin in LightDM](http://askubuntu.com/q/51086/235)
    after the fact so that when your machine boots it goes right into
    Steam’s Big Picture mode.

We’re using Valve’s xpad module instead of xboxdrv because that’s what
they use in SteamOS and I don’t want to deviate too much. But if you
prefer about xboxdrv then [follow this
guide](http://www.omgubuntu.co.uk/2014/06/ubuntu-xbox-controller-support-xboxdrv-driver).

-   Steam updates itself at the client level so there’s no need to worry
    about that, the final step for a console-like experience is to
    [enable automatic updates](http://askubuntu.com/q/9/235). Remember
    you’re using PPAs, so if you’re not confident that you can fix
    things, just leave it and do maintenance by hand every once in
    a while.

### Step 4: Home Theater Bling

If you’re going to have a nice living room box, then let’s use it for
other things. I have a dedicated server with media that I share out with
Plex Media Server, so in this step I’ll install the client side.

Plex Home Theater:

    sudo add-apt-repository ppa:plexapp/plexht
    sudo add-apt-repository ppa:ppa:pulse-eight/libcec
    sudo apt-get update && sudo apt-get install plexhometheater

In Steam you can then click on the + symbol, Add a non-steam game, and
then add Plex. Use the gamepad (not the stick) to navigate the UI once
you launch it. If you prefer XBMC/Kodi you can [install that
instead](http://wiki.xbmc.org/index.php?title=Installing_XBMC_for_Linux).
I found that the controller also works out of the box there, so it’s a
nice experience no matter which one you choose.

### Step 5: In Home Streaming

This is a killer Steam feature, that allows you to stream your Windows
games to your new console. It’s very straight forward, just have both
machines on and logged into Steam on the same network, they will
autodiscover each other, and your Windows games will show up in your
Ubuntu/Steam UI, and you can stream them. Though it works suprisingly
well over wireless, you’ll definately want to ensure you’ve got gigabit
ethernet if you want to stream games 1080p at 60 frames per second.

Conclusion
----------

And that’s basically it! There’s tons of stuff I’ve glossed over, but
these are the basic steps. There’s lots of little things you can do,
like remove a bunch of desktop packages you won’t need (so you don’t
need to download and update them) and other tips and tricks, I’ll try to
keep everyone up to date on how it’s going.

Enjoy your new next-gen gaming console!

![](http://www.jorgecastro.org/images/xcom.jpg)

TODO:

-   You can change out the plymouth theme to use [the one for
    SteamOS](http://repo.steampowered.com/steamos/pool/main/p/plymouth-themes-steamos/) -
    but I have an SSD in the box and combined with the fast boot it
    never comes up for me anyway.
-   It’d be cool to make a prototype of Ubuntu Core and then provide
    Steam in an LXC container on top of that so we don’t have to use a
    full blown desktop ISO.

</div>

<div class="share">

<div class="addthis_toolbox addthis_default_style">

[](){.addthis_button_tweet} [](){.addthis_button_google_plusone}
[](){.addthis_counter .addthis_pill_style}

</div>

</div>

<div id="comment" class="section">

<div id="disqus_thread" aria-live="polite">

Please enable JavaScript to view the [comments powered by
Disqus.](http://disqus.com/?ref_noscript)

</div>

</div>

</div>

</div>

Copyright © 2015 - Jorge O. Castro - <span class="credit">Powered by
[Octopress](http://octopress.org)</span>

Design credit: [Shashank
Mehta](http://shashankmehta.in/archive/2012/greyshade.html)

</div>

</div>
