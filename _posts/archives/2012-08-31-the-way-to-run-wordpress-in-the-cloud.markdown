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

Today [Marco Ceppi](http://marcoceppi.com/) finished up the new and
improved [WordPress
Charm](http://jujucharms.com/charms/precise/wordpress) in the juju charm
store. Feel free to throw away whatever Wordpress tutorial you’ve been
finding on the web, this is *the* easiest and most performant way to run
WordPress on Ubuntu (at least until you tells us better and we can
improve it, heh).

![](http://www.jorgecastro.org/images/wordpress.png)

### Set up and tuning

It’s pretty straightforward, set up your environment for
[AWS](https://juju.ubuntu.com/docs/getting-started.html), [HP
Cloud](http://askubuntu.com/q/116174/235), or
[OpenStack](http://askubuntu.com/q/132411/235), or bare metal and just
deploy it:

    juju deploy wordpress
    juju deploy mysql
    juju add-relation wordpress mysql
    juju expose wordpress

This gives you WordPress in a single configuration. Pulled from
upstream’s latest release and served with Nginx microcache, APC OpCode
caching, WordPress caching module, and the ability to sync files via
NFS.

This allows you to deploy a very fast configuration out of the box. It’s
probably better than most of the out-of-the-box set ups you’ve seen
around the web. This configuration is designed for small scale, so you’d
run it on a small or medium and just `juju add-unit wordpress` when you
get a traffic spike.

But what about larger sites, like say OMG!Ubuntu-like traffic? Ok. We’ve
[done this
before](http://www.jorgecastro.org/2012/03/22/iterating-deployment-with-juju)
and learned a ton, and now thanks to Marco all the lessons learned are
now deployable to every Ubuntu user. Here we go:

    juju set wordpress tuning=optimized

… and now your environment reconfigures itself to run in a multinode
wordpress configuration designed to be admin’ed by multiple users with
load balancing. The works. Want the basics with no options so you can do
it yourself? Here you go, nothing but raw vanilla wordpress and nginx:

    juju set wordpress tuning=bare

Want to stick your wp-content in version control? No worries with built
in bzr and git support:

    juju set wordpress wp-content=git@host:path/repo.git

or juju set wordpress wp-content=lp:\~username/path/repo

Now you have your content in version control. You can find all the
configuration options and how to use the charm on the [charm’s
page](http://jujucharms.com/charms/precise/wordpress), including a hack
for running it all on one node for those of you trying to maximize your
dollar.

### Rocking with memcached

Putting memcached with Wordpress is a best practice for caching high
traffic sites, you can add this with:

    juju deploy memcached
    juju add-relation memcached wordpress

Marco adds:

> This will automagically install WP-FFPC (regardless of your tuning
> settings) and configure it to cache rendered pages to the memcache
> server. In addition to this layer of caching, Nginx will pull directly
> from memcache bypassing PHP altogether.

### Dive in

Think you can do a better job optimizing Wordpress? Here’s [the
code](https://bazaar.launchpad.net/~charmers/charms/precise/wordpress/trunk/files),
and here’s how to [submit fixes and
improvements](https://juju.ubuntu.com/docs/charm-store.html#submitting-a-fix-to-an-existing-charm).
This charm is already better than any WordPress we’ve shipped in Ubuntu,
and we’re confident that through peer review and testing that it will
continue to get better. Remember folks, the Charm Store doesn’t freeze,
you can enjoy these improvements *today*; that means when Marco is done
with the [glusterfs
charm](http://jujucharms.com/~marcoceppi/precise/gluster) that you can
just switch to it if NFS isn’t your thing. It’s like cloud Legos!

Thanks to Marco Ceppi for backporting all the scaling lessons back into
the store for 12.04 users, and thanks to Brandon Holtsclaw for iterating
and testing a great deal of this, and for Joey for going all in with
this idea. As [I explained
before](http://www.jorgecastro.org/2012/04/03/the-juju-charm-store-will-change-the-way-you-use-ubuntu-server),
this changes everything. New WordPress release?
`juju upgrade-charm wordpress` and you’re good to go. You get pure fresh
WordPress with all the goodness out of the box, and then the OS gets out
of your way.

This is just the beginning, over the next few weeks you’ll see optimized
nginx and [optimized
nagios](http://fewbar.com/2012/08/juju-and-nagios-sittin-in-a-tree-polling-your-nrpe/)
start to hit as we start to really “go deep” into charm scaling and
quality. It will be an exciting time as we totally deprecate wide swaths
of “How to run \$foo on Ubuntu” around the web and get the goodness in
the charm store where anyone can deploy it.

You can catch Marco’s talk about juju and this charm at the [Washington
DC PHP Meetup](http://www.meetup.com/DC-PHP/events/39216022/) for those
of you in the beltway.

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
