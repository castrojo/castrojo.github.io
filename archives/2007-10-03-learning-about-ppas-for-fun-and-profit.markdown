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

I have been investigating some of the ways people can use
[launchpad](http://www.launchpad.net) to do cool stuff. About a month
ago my friend Flavio daCosta inquired about Novell’s kickass clock,
intlclock:

![Intlclock](http://stompbox.typepad.com/photos/uncategorized/2007/10/03/intlclock.png)

Neat huh? He had to apply some changes to get it to build in gutsy, and
we decided that we should go through the entire process together to try
to understand how bzr and launchpad work together.

So we [registered](http://launchpad.net/intlclock) it on launchpad, we
designated my bzr branch as “trunk”, and then Flav registered his own
branch to do some feature work. We even managed to pry Ken VanDine away
from hg for a few minutes, and then he too had a branch, this time with
some de-yastification patches (We need to call the Ubuntu time config
thing, not yast.)

-   time passes \*

Today I realized “Oh, I better set up that ppa so we can have binaries
for people” Three more people had registered bzr branches on launchpad.
I was able to inspect their branches, which were packaging fixes mostly,
and merge them right into my branch. Then I pushed it back out, and now
ppa is building the binaries.

I have no idea who those three people are, I had never met them in my
life. Yet while Flav, Ken and I were busy doing other stuff, people
stumbled across this on launchpad and just fixed stuff up.

\*\*Why I think this is cool:\
\*\*

Ever look for something and you end up with a .deb package attached to a
45 page thread on the forums? Then it ends up it’s from 2 years ago or
something and whoever made the deb left it around? Or the guy built it
for amd64 and you’re running i386 or something?

I can get hit by a truck tomorrow and the community can continue to
maintain the package and then publish them to a PPA. Users can follow
their favorite PPAs for software that they want, and no more out-of-date
attachments on the internet! And this is just a clock, wait until you
see the [other stuff](https://edge.launchpad.net/ubuntu/+ppas)!

You can play with the clock by adding this url to your software sources,
the package name is “intlclock”:

> deb http://ppa.launchpad.net/jorge/ubuntu gutsy main restricted
> universe multiverse

There’s an issue with not being able to set the time right now (doh!),
but top men are looking into it. This ppa will only be around for gutsy
because our friendly neighborhood GNOME developers will be putting this
upstream by default for 2.22!

Link: [PPA Quickstart Guide](https://help.launchpad.net/PPAQuickStart)

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
