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

Ok so we’ve fleshed out the [MAAS wiki
page](https://wiki.ubuntu.com/ServerTeam/MAAS) a bit today with some
instructions on how to get started. If you’ve got a few boxes around
(You’ll likely need at least 3 boxes, one for MAAS, and then two nodes
for juju, though you only need 2 to test MAAS by itself.). If you don’t
know what MAAS is then you can check out Mark’s [blog
post](http://www.markshuttleworth.com/archives/1103) about it. It’s a
new provisioning tool that lets you quickly deploy servers.

MAAS itself is easy to install, just a `sudo apt-get install maas` and
you’re good to go. Like other deployment tools it helps if you’re in
control of your own DNS/DHCP server, though I was able to get it running
by just setting them up on their own separate network.

After you’ve got your shiny new MAAS server running we could use a hand
with some testing. We’ve documented that here:

-   <https://wiki.ubuntu.com/SecurityTeam/TestingMAAS>

What you’ll do is install an updated checkbox from a PPA and then submit
a few tests:

![](http://www.jorgecastro.org/images/checkbox.png)

And then do some tests:

![](http://www.jorgecastro.org/images/tests.png)

If we fail a test we take you right to launchpad where you can file a
bug, and then we’ll go fix them. So if you’ve got some boxes sitting
around and want to help out do feel free to join in; but remember this
is a deployment system, so blowing away your machines and installing
Ubuntu Server on them is desired behavior, so don’t sacrifice boxes you
might care about.

Giving Feedback
---------------

If you’d like to give feedback, comments or even patches, get in touch
with the team on launchpad at <https://launchpad.net/~maas-devel>. We’re
keen on learning what you’d like to see MAAS do.

Happy MAASing!

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
