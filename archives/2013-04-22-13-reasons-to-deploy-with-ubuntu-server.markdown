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

Sometimes people ask me why they should use Ubuntu Server. It’s an
understandable question, after all, Ubuntu gets a bunch of attention on
the desktop (and more recently mobile), but people tend to forget that
Ubuntu is an excellent server distribution, quietly humming along
helping to running some of the world’s coolest companies at scale.

So I thought I’d document why you should choose Ubuntu for your
organization. Paul Hammond from TypeKit [has
said](http://www.paulhammond.org/2012/startup-infrastructure/startups.pdf)
“No startup has cever failed because they picked the wrong linux
distribution.” TypeKit’s linux of choice? Ubuntu. So why is that? So I
started to think of reasons why you would choose Ubuntu, and to
celebrate the release of 13.04, I came up with 13 major reasons you
would choose to go with us. Let’s get started, in no particular order!

OpenStack and the cloud archive
===============================

As I said a [few weeks
ago](http://www.jorgecastro.org/2013/04/09/looking-to-deploy-openstack-ubuntu-has-you-covered/),
shipping a well tested robust OpenStack is one of our primary missions.
We’ve been shipping OpenStack in Ubuntu for over X years now, and every
cycle we get better at it. We do *daily* and *per commit* automated
testing of OpenStack.

We’re [committed](https://wiki.ubuntu.com/ServerTeam/CloudArchive) to
backporting the latest OpenStack releases to Ubuntu 12.04 LTS (Long Term
Support). That means if you want the fresh upstream goodness of
OpenStack but want a stable platform, you can get that with Ubuntu; no
one else is doing anything like this.

How ready is OpenStack and Ubuntu for production? It’s there, and we
know that because we’re running [OpenStack in
production](http://www.openstack.org/summit/portland-2013/session-videos/presentation/canonical-keynote-openstack-in-production).
Moving from a traditional IT setup to “devops” using the cloud is tough,
and we’re still in the process of doing it, we learned a bunch of best
practices that we’ve shared with the community, see Robbie Williamson’s
talk: \[OpenStack in Production: the Good, the Bad & the Ugly\]
(http://openstacksummitapril2013.sched.org/event/ae0f3fb59942bca70d9befb18fd2bbfd\#.UWVryUnMLoc)

Ceph
====

![](http://www.jorgecastro.org/images/ceph.png)

Ceph is a [massively scaleable distributed file
system](http://en.wikipedia.org/wiki/Ceph_%28storage%29) that runs on
commodity hardware. And it [comes with
Ubuntu](http://www.inktank.com/news-events/new/ceph-included-in-ubuntu-12-04-lts/)
in main and is fully supported by Canonical and Inktank. Here is the
[blueprint](https://blueprints.launchpad.net/ubuntu/+spec/servercloud-r-ceph)
if the usecases we are enabling out of the box. We’re also working on
getting per-commit and daily automated testing of Ceph as well.

I am doing Ceph a disservice by only mentioning it in one paragraph. The
sheer capabilities of Ceph and it’s scalability can take up pages, so if
you’re looking to get started with Ceph, check out this tutorial from
Inktank on how they [deploy Ceph with
Juju](http://ceph.com/dev-notes/deploying-ceph-with-juju/) and check it
out for yourself.

MAAS
====

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

Juju and its charms
===================

![](http://www.jorgecastro.org/images/juju-logo.png)

And this is where it comes together. You’ve got your OpenStack running
with tons of nodes, exabytes of storage on Ceph, no what? No one builds
a cloud for the sake of building one. You have *work to do*, and that’s
what Juju is all about.

Juju takes all this infrastructure you just set up and makes you …. not
care about it. Juju bucks the trend of thinking about machines and
instances as a whole. We back you up and show you a higher level view of
your deployment and get you to think about what’s really important to
your business, deploying *services*.

![](http://www.jorgecastro.org/images/juju-gui/1.png)

So now you think of your deployment as environments, like Hadoop,
Cassandra, MongoDB, or \$your\_application. You tell Juju how to model
your deployment, and it uses all the things I just mentioned, MAAS,
OpenStack, your public cloud provider, to make your environment. You
manage things at the service level. Just assemble your blocks and the
juju scripts (we call them charms) do the rest.

So what’s that mean for you? Here’s an example of how you can deploy
[your node.js app](http://jujucharms.com/charms/precise/node-app) or
[your rails app](http://jujucharms.com/charms/precise/rails). What you
see there is our end goal for everyone who wants to deploy anything to
the cloud can do so in a few commands or a few mouse clicks. We’re well
on our way with over [120
services](http://jujucharms.com/charms/precise) available for you to
start to put together.

Here’s an example of setting up [sharding with
MongoDB](http://blog.xtremeghost.com/2012/11/lets-shard-something.html)
if you really want to see how Juju takes the complexity out of service
orchestration.

Hardware Enablement Stack
=========================

Ubuntu provides what we call an [LTS Enablement
Stack](https://wiki.ubuntu.com/Kernel/LTSEnablementStack).

Simply stated, we provide newer kernels for the Long Term Support
release, that means if you end up with newer hardware that needs newer
hardware support you can still use an LTS release and have a stable
userspace. The enablement kernels then provide you an upgrade path for
the next LTS.

For more tips on how to use these stacks, check out [this blog
post](http://www.jorgecastro.org/2013/02/19/what-the-lts-enablement-stack-means-for-sysadmins/).

Hardware Certification
======================

We’re certified to run on hardware from the top names in servers. Dell,
HP, Lenovo, IBM, and Acer are just some of [our certification
partners](http://www.ubuntu.com/certification/server/).

ARM
===

We’ve been building Ubuntu on ARM as a fully functional, well tested OS
that can support multiple SoCs (Calxeda, TI, Marvell Armada XP, and
anything Ubuntu Touch/Client uses) – and have been doing so for over 4
years.

We’re working with Calxeda on their [ECX-1000 EnergyCore Products
(Highbank)](http://www.calxeda.com/technology/products/processors/ecx-1000-series/).
We are going to be using the ECX-1000 as our ARM server reference
platform for 13.04.

![](http://www.calxeda.com/wp-content/uploads/2012/05/Capture3847_large-300x199.jpg)

And we’ll be working with them on their “Midway” product refresh when
that hits.

Ubuntu Guest on Public Clouds
=============================

![](http://www.jorgecastro.org/images/providers.png){.right}

Whether it’s like Amazon Web Services, HP Cloud, Rackspace, Internap, or
Microsoft Windows Azure, you’ll find official Ubuntu images, and you’ll
find that the per-hour cost to you is \$0.00.

The nice thing we do in the public clouds is that we work closely with
the cloud providers to give you a nice experience. Our images are
directly published into these clouds as part of the release process,
they’re not made after-the-fact. And since it’s Ubuntu, it’s *the same*
on every cloud, you won’t find different behavior from your local
servers or from vendor to vendor, it’s important to us to provide you a
consistent experience.

One the certified public clouds you’ll not only find regularly refreshed
and supported images, you’ll find other goodies, like built in local
mirrors so that your updates are LAN speed in your cloud deployments.
And since we partner with these providers and continually work with them
to improve on this experience you’re covered.

LXC/Containers and Vagrant
==========================

It seems that a bunch of the things I’ve been talking about are ops
focused. Juju straddles both dev and ops, it’s why we call it “DevOps
Distilled”. I’d like to point out some of the nice things that are
useful for developers as well.

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
=========

Ubuntu and its community
========================

In a way, Ubuntu itself is a feature.

-   There is no “enterprise” and “free” versions of Ubuntu. It’s all
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
================

As I mentioned above, since Ubuntu is free-to-use we are extremely
motivated to provide service thats offer a good value. Our service
offerings are split into two areas, server and cloud:

Here are our prices for [traditional
servers](http://www.ubuntu.com/business/server/services), starting as
low as \$320 per box. And here are our [cloud
prices](http://www.ubuntu.com/cloud/solutions). You can also add on
Landscape and what we call Premium Service Engineers. PSEs are our
best-of-the-best. If you need an expert to solve your toughest problems,
you can add on a PSE.

Shop around and check out our competitor’s too, you’ll find that our
prices very competitive.

You’re in fine company
======================

Along with Netflix, Wikipedia, Inktank, AT&T, HP, Dreamhost, Rackspace,
Instagram, Dropbox, SmugMug, HP, Samsung, NTT, Deutsche Teleko, 10gen,
and Amazon all chose Ubuntu Server because of things like I mentioned
above.

So that’s the jist folks. Ask you can tell we’re pretty excited about
the things we’re bringing to the cloud and your server room. We’re one
year away from our next Long Term Support (LTS) release and committed to
bring all of these technologies to bear. Some of them have in the cooker
for a bit (MAAS and Juju) and are still under heavy feature development,
so if you were an early adopter and been burned by a bug or lack of a
feature, now is the time to start looking at it again and giving us
feedback. As the Fall approaches we’ll be shifting to getting ready for
14.04 LTS and keep on pushing the envelope of the cloud.

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
