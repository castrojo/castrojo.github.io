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

I started off yesterday detailing the [first four
reasons](http://www.jorgecastro.org/2013/04/29/13-reasons-to-deploy-with-ubuntu-server/)
why you’d want to consider deploying with Ubuntu Server. Here are
today’s four.

Juju and its charms
-------------------

![](http://www.jorgecastro.org/images/juju-logo.png)

And this is where it starts to comes together. You’ve got your OpenStack
running with tons of nodes, exabytes of storage on Ceph, now what? No
one builds a cloud for the sake of building one. You have *work to do*,
and that’s what Juju is all about.

Juju takes all this infrastructure you just set up and makes you… not
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
the cloud - you should be able to do so with a few commands or a couple
of mouse clicks. We’re well on our way with over [120
services](http://jujucharms.com/charms/precise) available for you put
together, and plenty more on the way. All of them are Free Software,
ready to be improved upon and shared with the wider community.

Here’s an example of setting up [sharding with
MongoDB](http://blog.xtremeghost.com/2012/11/lets-shard-something.html)
if you really want to see how Juju takes the complexity out of service
orchestration.

Hardware Certification
----------------------

We’re certified to run on hardware from the top names in servers. Dell,
HP, Lenovo, IBM, and Acer are just some of [our certification
partners](http://www.ubuntu.com/certification/server/). There’s not
really much else to say. This bullet seems really boring, but it’s
certainly not boring for the people in our hardware labs, this is just
something most sysadmins will expect to work out of the box.

ARM
---

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
-----------------------------

![](http://www.jorgecastro.org/images/providers.png){.right}

Whether it’s like Amazon Web Services, HP Cloud, Rackspace, Internap, or
Microsoft Windows Azure, you’ll find official Ubuntu images, and you’ll
find that the per-hour cost to you is \$0.00.

The nice thing we do in the public clouds is that we work closely with
the cloud providers to give you a great experience. Our images are
directly published into these clouds as part of the release process,
they’re not made after-the-fact. And since it’s Ubuntu, it’s *the same*
on every cloud, you won’t find different behavior from your local
servers or from vendor to vendor, it’s important to us to provide you a
consistent experience.

On the certified public clouds you’ll not only find regularly refreshed
and supported images, you’ll find other goodies, like built-in local
mirrors so that your updates are LAN speed in your cloud deployments.
And since we partner with these providers and continually work with them
to improve on this experience you’ll always be getting the best
available service.

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
