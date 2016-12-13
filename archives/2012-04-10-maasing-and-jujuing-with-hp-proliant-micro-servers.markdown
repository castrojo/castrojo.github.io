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

I’ve heard nothing but good things about [HP Proliant N40L
Microservers](http://h10010.www1.hp.com/wwpc/us/en/sm/WF06b/15351-15351-4237916-4237918-4237917-4248009-5153252-5153253.html?dnr=1).
Those of you who have ever spent more than 5 minutes with popey know
he’s all about them. They seem like great little boxes; quiet, Hold 4+1
drives, and with an optional ilo card can be totally headless. Add
drives and some Ubuntu server and you’re good to go. Or in Robbie’s
case, a few of them with Ubuntu Server and OpenStack:

![](http://www.jorgecastro.org/images/robbie_proliant.jpg)

Compared to my meager set up:

![](http://www.jorgecastro.org/images/jorge_proliant.jpg)

Anyway; the Proliant comes with 4 drive bays. Unfortunately one of them
is for the OS drive, and yet it comes with an entire empty top part
where they expect you to put an optical disc drive, which in today’s
world of [MAAS](https://wiki.ubuntu.com/ServerTeam/MAAS) is a waste of
space, since we’re all about managed PXE installs now. So if you want to
put an OS drive there instead, you’ll want [this bit of
kit](http://www.amazon.com/Professional-3-5-Inch-Universal-Mounting-5-25-Inch/dp/B005F9Q8HU/ref=pd_ecc_rvi_cart_3)
so you can stick an OS drive in there and then have the slick bays open
for data disks. You’ll need a right angle SATA cable and MOLEX-&gt;sata
power converter as well, which is why mine is still in pieces. A nice
external eSATA port means I can also just reuse my old existing
enclosure.

While Robbie will surely be jujuing on his openstack, I will be using my
micro to deploy the same juju charms, except as LXC containers. Since
juju abstracts the cloud provider stuff from me, I can prototype my
little deployments on my server and be reasonably certain that my stuff
will be OpenStack-ready, except for scale of course, I couldn’t test a
40 node Hadoop deployment on my server. But I can certainly deploy most
things.

If you work at HP and are reading this, give me a little slot on the
side for an SSD OS drive and I’ll be a happy clam. Preloaded with Ubuntu
Server and I’d be even happier. :)

(Note, this post has nothing to do with the previous XBMC post,
whatsoever. &gt;\_&gt; )

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

Copyright © 2016 - Jorge O. Castro - <span class="credit">Powered by
[Octopress](http://octopress.org)</span>

Design credit: [Shashank
Mehta](http://shashankmehta.in/archive/2012/greyshade.html)

</div>

</div>
