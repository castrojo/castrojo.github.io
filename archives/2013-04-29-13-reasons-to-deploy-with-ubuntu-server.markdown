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

(Part 1 of 3)

Sometimes people ask me why they should use Ubuntu Server. It’s an
understandable question, after all, Ubuntu gets a bunch of attention on
the desktop (and more recently mobile), but people tend to forget that
Ubuntu is an excellent server distribution, quietly humming along
helping to run some of the world’s coolest companies at scale.

So I thought I’d document why you should choose Ubuntu for your
organization. Paul Hammond from TypeKit [has
said](http://www.paulhammond.org/2012/startup-infrastructure/startups.pdf)
“No startup has ever failed because they picked the wrong Linux
distribution.” TypeKit’s Linux of choice? Ubuntu. Why is that? So I
started to think of reasons why you would choose Ubuntu, and to
celebrate the release of 13.04, I came up with 13 major reasons you
would choose to go with us. Let’s get started, in no particular order!
I’ll split this post over the next few days so you can digest it easier,
and more importantly, go play with the things I talk about!

OpenStack and the cloud archive
-------------------------------

As I said a [few weeks
ago](http://www.jorgecastro.org/2013/04/09/looking-to-deploy-openstack-ubuntu-has-you-covered/),
shipping a well tested and robust OpenStack is one of our primary
missions. We’ve been shipping OpenStack in Ubuntu for over 3 years now,
and every cycle we get better at it. We do *daily* and *per commit*
automated testing of OpenStack. Maybe that’s one of the reasons Ubuntu
is the reference OS for OpenStack.

We’re [committed](https://wiki.ubuntu.com/ServerTeam/CloudArchive) to
backporting the latest OpenStack releases to Ubuntu 12.04 LTS (Long Term
Support). That means if you want the fresh upstream goodness of
OpenStack but want a stable platform, you can get that with Ubuntu; no
one else is doing anything like this.

How ready is OpenStack and Ubuntu for production? It’s there, and we
know that because we’re running [OpenStack in
production](http://www.youtube.com/watch?feature=player_embedded&v=Gi2eoDU0xXM).
Moving from a traditional IT setup to “devops” using the cloud is tough,
and we’re still in the process of doing it, we learned a bunch of best
practices that we’ve shared with the community, see Robbie Williamson’s
talk: [OpenStack in Production: the Good, the Bad & the
Ugly](http://www.youtube.com/watch?v=7GWyL-AzyO4)

Ceph
----

![](http://www.jorgecastro.org/images/ceph.png)

Ceph is a [massively scaleable distributed file
system](http://en.wikipedia.org/wiki/Ceph_%28storage%29) that runs on
commodity hardware. And it [comes with
Ubuntu](http://www.inktank.com/news-events/new/ceph-included-in-ubuntu-12-04-lts/)
in main and is fully supported by Canonical and Inktank. Here is the
[blueprint](https://blueprints.launchpad.net/ubuntu/+spec/servercloud-r-ceph)
of the usecases we are enabling out of the box. We’re also working on
getting per-commit and daily automated testing of Ceph as well.

I am doing Ceph a disservice by only mentioning it in one paragraph. The
sheer capabilities of Ceph and it’s scalability can take up pages, so if
you’re looking to get started with Ceph, check out this tutorial from
Inktank on how they [deploy Ceph with
Juju](http://ceph.com/dev-notes/deploying-ceph-with-juju/) and check it
out for yourself.

MAAS
----

![](http://www.jorgecastro.org/images/maas-logo.png)

On the local server front, we provide a provisioning tool called
[MAAS](https://maas.ubuntu.com/), which stands for Metal-as-a-Service.
MAAS not only provisions bare metal machines for you (on demand), but we
like to say it “brings the language of the cloud to physical services”.
Sometimes you just want the ability to horizontally scale as demand
comes in, and have machines turn on, install the OS, and then get to
work, all automatically.

We use MAAS to deploy OpenStack, or you can use MAAS to deploy whatever
servers you need, e.g. Hadoop or Ceph, on whatever scale-out hardware
you have, e.g. Intel, AMD, or ARM, all programatically. It’s a simple
but powerful tool to deliver provisioned servers to you.

Hardware Enablement Stack
-------------------------

Ubuntu provides what we call an [LTS Enablement
Stack](https://wiki.ubuntu.com/Kernel/LTSEnablementStack).

Simply stated, we provide newer kernels for the Long Term Support
release, that means if you end up with newer hardware that needs newer
hardware support you can still use an LTS release and have a stable
userspace. The enablement kernels then provide you an upgrade path for
the next LTS.

For more tips on how to use these stacks, check out [this blog
post](http://www.jorgecastro.org/2013/02/19/what-the-lts-enablement-stack-means-for-sysadmins/).

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
