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
-   [My beagle, Oscar](http://packdog.com/oscar-castro)
-   -   [My bagel, Luna](http://packdog.com/luna-330)
-   

\
### Projects I work on

-   [Ubuntu Server](http://ubuntu.com/server)
-   [Juju](http://jujucharms.com)
-   [Juju Charms](http://jujucharms.com/store)
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

It seems
[people](http://www.stefanoforenza.com/jackalope-jaunty-to-boot-faster-than-the-time-i-took-to-write-this-headline-kinda/)
are
[noticing](http://www.mattcutts.com/blog/ubuntu-904-boots-in-175-seconds/)
how much faster 9.04 is at booting.

I happen to have 2 SSD disks, one in my desktop and one in the laptop. I
measured both my machines with [bootchart](//bootchart), the laptop is
set to autologin (I am unsure when bootchart stops measuring or if that
matters).

The desktop is a 32gb Samsung SLC drive:
[12.54](http://dl.getdropbox.com/u/5720/cooler-jaunty-20090413-1.png)
seconds. Not so bad. This is kind of a mongrel system though, I am
always installing and removing things, which is why you see leftover
exim stuff. I also use a spinning disk as my /home, but I do symlink
things like .gconf and .config that get read on boot to make that fast.
(And yes, moving .gconf from the spinning disk to the SSD made a huge
difference “feel” wise, I should have measured that.) Either way, it’s
not a good candidate for measuring stuff, so take that with a grain of
salt.

My Lenovo X200 has an X25-M (Not the faster E mind you) - [7.61
seconds](http://dl.getdropbox.com/u/5720/watson-jaunty-20090413-1.png).
This is basically stock Ubuntu 9.04 as of this morning. Quite
acceptable.

For those of you in the back going “Come on now, you have SSDs, I am
just a normal person with normal disks, no fair!” I have an old athlon
system in the other room and a hp 2510p laptop with a notoriously slow
4200rpm drive and I notice the difference on both of them. Unfortunately
you’re going to have to take my word for it since I never had bootchart
installed on them until just now. Even in Jaunty the boot time of the
2510p is 27.98 seconds, just to give you an idea …

</div>

<div class="share">

<div class="addthis_toolbox addthis_default_style">

[](){.addthis_button_tweet} [](){.addthis_button_google_plusone}
[](){.addthis_counter .addthis_pill_style}

</div>

</div>

</div>

</div>

Copyright © 2016 - Jorge O. Castro - <span class="credit">Powered by
[Octopress](http://octopress.org)</span>

Design credit: [Shashank
Mehta](http://shashankmehta.in/archive/2012/greyshade.html)

</div>

</div>
