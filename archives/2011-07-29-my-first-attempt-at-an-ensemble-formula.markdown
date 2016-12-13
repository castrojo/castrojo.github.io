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

Since
[every](http://foss-boss.blogspot.com/2011/07/ubuntu-takes-ufos-to-cloud.html)
[one](http://s3hh.wordpress.com/2011/07/29/playing-with-ensemble/)
[else](http://blog.markmims.com/cloud/2011/07/12/hadoop-on-ubuntu.html)
is doing it, I thought I’d play with more Ensemble tonight, but instead
of firing something up I started working on a formula for
[summit](http://summit.ubuntu.com), the tool we used to schedule UDS.

First Chris Johnston and Michael Hall started an
[etherpad](http://pad.ubuntu.com/BaSLqQuo7d) with the instructions for
installing summit (and we’re doing one for the LoCo directory too since
we like biting off more than we can chew).

Here’s the [first
cut](http://bazaar.launchpad.net/~jorge/+junk/summit-ensemble/view/head:/hooks/install)
of the install script based on those instructions, then I went ahead and
ran it in a VM to make sure it worked non-interactively. The
documentation recommends that [you have a
plan](https://ensemble.ubuntu.com/docs/write-formula.html#have-a-plan) before
you start. Basically you are scripting an install on a brand new OS
installation so you have to think of things you might normally take for
granted, like remembering to install bzr or git before you pull
something, heh:

> When attempting to write a formula, it is beneficial to have a mental
> plan of what it takes to deploy the software. In our case, you should
> deploy drupal manually, understand where its configuration information
> is written, how the first node is deployed, and how further nodes are
> configured. With respect to this formula, this is the plan.

I did ok until I got to the `python manage.py syncdb` part of summit,
which asked me a question, but not bad for the first shot. 

Of course, had I picked something packaged it wouldn’t be so
complicated, my install script would just be an apt-get command but I
think it’s useful to be able to just fire off an instance of summit
right from trunk. 

The ability to just grab whatever you want right from trunk and fire off
an instance is pretty powerful, I’m looking forward to seeing James
Page’s etherpad-lite formula be ready so anyone can just fire one up for
\$your-favorite-conference.

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
