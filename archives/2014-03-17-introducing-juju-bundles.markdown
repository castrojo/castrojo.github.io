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

“Rick, I want you to fire up an empty cloud deployment”, said no boss
ever.

The various teams who make up “The Ubuntu Server Team” work on various
bits. Some work to make OpenStack easy to deploy, some work on
packaging, some work on building images for all the public clouds we
support. All this is fine and dandy, but at the end of the day, our
users deploy things on top of Ubuntu Server, and these workloads are
really what it’s all about.

Over the past two years it’s been increasingly obvious to us that
orchestrating workloads is becoming one of the most important things we
can help users with. What’s the point of an easy to use OpenStack
installer if people can’t plop Hadoop, or Cassandra, or their Rails app
right on top easily?

One part of this solution is our work on [Juju](http://juju.ubuntu.com),
which makes orchestration simple; we can just manage deployments at the
service level while not caring (too much) about individial instances.
Some people wanted and needed things to be even highter level. “Look,
I’ve got a pile of machines over here, I need a MongoDB cluster” and you
don’t have the time! Or more increasingly, you know how to do all these
steps, but need a way to make it portable so everyone else in your
organization can benefit from your hard work.

So today we [announced Juju
Bundles](http://insights.ubuntu.com/news/juju-bundles-and-quickstart-create-an-entire-cloud-environment-in-seconds/).
Technically, they’re very simple, it’s a yaml file that describes charms
and their relationships to other charms. It can contain machine
constraints, or any of the parameters you’d ship in a charm. That means
deploying large swaths of services are now *one command*.

    juju quickstart bundle:~charmers/mongodb/cluster
    juju quickstart bundle:~charmers/hadoop/cluster
    juju quickstart bundle:~charmers/mediawiki/scalable

There’s a 13 node 3 shard MongoDB cluster, a 7 node starter Hadoop
cluster, and a 5 node Mediwiki. All of them can be horizontally scaled
out of the box. `juju add-unit -n10 hadoop-slavecluster` and go to town.
Not Bad!

Getting Started
---------------

If you’re on Ubuntu [Rick has the
info](http://blog.mitechie.com/2014/03/17/juju-quickstart-and-the-power-of-bundles/)
in his blog post, you basically:

    sudo add-apt-repository ppa:juju/stable
    sudo apt-get update
    sudo apt-get install juju-quickstart

Then run one of the commands I mentioned:

    juju quickstart bundle:~charmers/mongodb/cluster

Juju will then walk you through setting up an environment. Pick one.
AWS, Microsoft Windows Azure, Joyent, HP Cloud, or your own OpenStack or
laptop via LXC, then fill out your creds:

![](http://www.jorgecastro.org/images/quickstart2.png)

Now get a cup of coffee, or watch the console for the magic, maybe read
the [README](https://jujucharms.com/precise/mongodb/#readme).

![](http://www.jorgecastro.org/images/mongo-cluster-bundle.png)

Now go put that bad boy to work.

Quickstart is not yet available for OSX or Windows (we’re working on
it), but if you want to play with it we’ve made a [Vagrant box
available](https://juju.ubuntu.com/docs/config-vagrant.html) for you to
play with.

The Future
----------

Over the course of the next few weeks as we ramp up to 14.04 we’ll be
doing a few things. We’ll be tightening up the URLs to be easier to
remember, so something like `juju quickstart bundle:mongodb/cluster`.
Obviously we’d love to see more bundles from the community being
submitted.

Check out [the
documentation](https://juju.ubuntu.com/docs/charms-bundles.html) for
more, and for a more technical description of how bundles work check out
[Rick’s blog
post](http://blog.mitechie.com/2014/03/17/juju-quickstart-and-the-power-of-bundles/).
We also made a [tutorial
video](https://www.youtube.com/watch?v=eYpnQI6GZTA) on how to make and
share your own bundles.

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
