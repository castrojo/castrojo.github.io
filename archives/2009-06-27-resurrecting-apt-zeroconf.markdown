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

I have been toying with a bunch of apt-proxy-like things since I read
[jdub’s
blog](http://bethesignal.org/blog/2009/04/13/approx-package-caching-ubuntu-debian-lovers/)
about approx. apt-cacher-ng seemed to be working but tends to wonk out
on occasion. I decided to try squid for a bit (because then I could use
it to cache other things, not just debs).

So after a while of messing with this stuff I decided “this is dumb, why
aren’t the computers just maintaining themselves, I am doing too much
work for this crap.” I didn’t want to go computer to computer setting a
proxy and I didn’t want to mess around with a transparent proxy so I was
just annoyed. (And lazy!)

apt-zeroconf was doing this nice and automatically in the past but it
was dead upstream and the website disappeared. Maybe if someone fixed
this up this would be a nice little solution for home users with
multiple PCs. Ends up that [Jeremy
Austin-Bardo](https://edge.launchpad.net/~ausimage) had written a
[blueprint](https://blueprints.edge.launchpad.net/ubuntu/+spec/personalpackagecache)
and a spec. So I gave him a call and now we have started a project to
resurrect apt-zeroconf.

[Here it is](https://launchpad.net/apt-zeroconf).

The idea is simple. On your home machines you check a box in the gui
someplace, and then all your machines share their apt packages with each
other. Which means that on release day you upgrade one machine, and then
when you upgrade the others you don’t have to redownload everything
again. Nice huh? Combine this with deb delta syncing and you’ve got a
nice little bandwidth saving solution.

The project is small so some of the guys from the Michigan LoCo will be
looking into this as their summer project. If you know python and avahi
we could use your help. Also, something changed in pyinotify that we
can’t figure out, so help there would be appreciated. Branch away and
feel free to join the [team and mailing
list](https://launchpad.net/~apt-zeroconf) for updates.

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
