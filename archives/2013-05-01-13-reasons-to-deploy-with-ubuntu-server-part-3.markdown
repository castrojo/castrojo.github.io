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

LXC/Containers and Vagrant
--------------------------

It seems that a bunch of the things I’ve been talking about so far are
ops focused. Juju straddles both dev and ops, it’s why we call it
“DevOps Distilled”. I’d like to point out some of the nice things that
are useful for developers as well.

The first is our [LXC support](http://lxc.sourceforge.net/). You can
think of Linux containers as “super chroots”, that let you segment
whatever you want on a machine without the overhead of virtualization.
We can use it to segment your deployed services with Juju, or you can
use them to play with things in a nice little sandbox. And yes, we’ve
got our eyes on [Docker](http://www.docker.io/) too.

Speaking of sandboxes, we also now provide [official Vagrant
images](http://cloud-images.ubuntu.com/vagrant/) so you can quickly fire
up server instances on any OS to do your development on. And just like
the rest of our cloud images, frequently updated and fully supported.

Landscape
---------

Organizations need to manage large fleets of Ubuntu systems, and that’s
where [Landscape](http://ubuntu.com/landscape) comes in. As the usage of
Ubuntu server to deploy services scales out seamlessly through Juju,
your infrastructure needs day-to-day tending to.

Landscape lets you manage thousands of Ubuntu servers with the same ease
you would manage one - you can fix a security issue affecting hundreds
of machines with a single click, and what’s more you can prove you did
to your compliance or governance team without having to spend time
creating the paper trail yourself - that is a really big deal if you
work in an IT department and don’t enjoy spending your time creating
reports.

![](http://www.jorgecastro.org/images/landscape.png)

Landscape is designed from the ground-up to manage Ubuntu systems, and
that reflects on the tight integration between Ubuntu core components
and Landscape. In Ubuntu, we use `apt` to update systems from the shell
- Landscape talks to `apt`, not a different custom backend, so if you
know how `apt` behaves, you already know how Landscape does it - this is
a design style that makes the learning curve for Landscape much nicer
than other tools’ - and makes it inherently shell-compatible, for we
understand very well that an administrator’s debug tool of choice is
SSH.

Landscape’s management goodness is exposed through its server’s API -
providing you with a robust toolset of management actions that are
maintained for you across all current Ubuntu releases, from cutting edge
Raring to reliable and dependable Precise - any architectural
differences are taken care of for you, so you don’t have to.

Landscape is built for enterprises customers, and it has both SAAS and
Dedicated Server editions. A [free 30-day
trial](http://landscape.canonical.com) is available for those who want
to try first hand.

Ubuntu and its community
------------------------

Sounds kind of cheesy, but Ubuntu itself is a feature.

-   There are no “enterprise” and “free” versions of Ubuntu. It’s all
    just Ubuntu, and it’s all free to the end user. That’s right. We
    don’t artificially split the OS. If Ubuntu works out of the box for
    you and you’re skilled enough to use it, you’re good to go. You get
    the *exact* same OS, with the exactly same support that paying
    customers get. This does motivate us to provide excellent support
    options (see below).

Run into a problem? Well you can call us and get support, all without
having to reinstall from the “free version” to the “paid version”. No
shuffling licenses either or caring about which of your systems are
supported or covered, and no waiting for security fixes to trickle down
to your free version. Just pay for what you use.

-   cloud-init - You can control [instance
    initialization](https://help.ubuntu.com/community/CloudInit)
    with cloud-init. It’s like preseeding/kickstarting a server, but in
    the cloud.

-   The community - the massive resources of the Ubuntu community is
    available to you. And it’s not just about support, it’s about things
    like a wide range of PPA archives of contributed packages and
    ecosystem of packages for things that run on Ubuntu, but might not
    be part of the distro itself.

-   Built on [Debian](http://www.debian.org/). \`Nuff said. So you get
    nice things like tasksel tasks, allowing you to simply install Mail,
    Web Server, or LAMP stacks with one checkbox and the breadth of
    software of the Debian archive.

-   A predictable and solid release cycle, with 5 years of support for
    our LTS releases.

Ubuntu Advantage
----------------

As I mentioned above, since Ubuntu is free-to-use we are extremely
motivated to provide service that offers a good value. Our service
offerings are split into two areas, server and cloud:

Here are our prices for [traditional
servers](http://www.ubuntu.com/server/management), starting as low as
\$320 per box. And here are our [cloud
prices](http://www.ubuntu.com/cloud/management). You can also add on
Landscape and what we call Premium Service Engineers. PSEs are our
best-of-the-best. If you need an expert to solve your toughest problems,
you can add on a PSE.

Shop around and check out our competitor’s too, you’ll find that our
prices very competitive.

You’re in fine company
----------------------

Along with Netflix, Wikipedia, Inktank, AT&T, HP, Dreamhost, Rackspace,
Instagram, Dropbox, SmugMug, Samsung, NTT, Deutsche Telekom, 10gen, and
Amazon. They, and many others, chose Ubuntu Server because of some or
all of the things I mentioned above.

So that’s the jist folks. As you can tell we’re pretty excited about the
things we’re bringing to the cloud and your server room. We’re one year
away from our next Long Term Support (LTS) release and committed to
bring all of these technologies to bear. Some of them have been in the
cooker for a bit (MAAS and Juju) and are still under heavy feature
development, so if you were an early adopter and been burned by a bug or
lack of a feature, now is the time to start looking at it again and
giving us feedback. As the Fall approaches we’ll be shifting to getting
ready for 14.04 LTS and keep on pushing the envelope of the cloud.

Check out the previous sections if you missed them:

-   [13 Reasons to Deploy with Ubuntu Server Part
    1](http://www.jorgecastro.org/2013/04/29/13-reasons-to-deploy-with-ubuntu-server/)
-   [13 Reasons to Deploy with Ubuntu Server Part
    2](http://www.jorgecastro.org/2013/04/30/13-reasons-to-deploy-with-ubuntu-server-part-2/)
-   [13 Reasons to Deploy with Ubuntu Server Part
    3](http://www.jorgecastro.org/2013/05/01/13-reasons-to-deploy-with-ubuntu-server-part-3/)

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
