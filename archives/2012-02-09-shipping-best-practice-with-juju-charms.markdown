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

Check out [Why I don’t host my own blog
anymore](http://www.kalzumeus.com/2012/02/09/why-i-dont-host-my-own-blog-anymore/).

I mentioned it to a friend and he immediately piped in “Oh that guy did
it wrong, he shouldn’t care about KeepAlive, he needs FastCGI”.

Ok so the guy “messed up” and misconfigured his blog. Zigged instead of
zagged. Bummer.

But it doesn’t have to be this way. Right now we offer [Wordpress as a
juju charm](http://charms.kapilt.com/charms/oneiric/wordpress). This
lets us deploy Wordpress with Mysql in 4 commands.

However if you look at the
[db-relation-hook](http://charms.kapilt.com/charms/oneiric/wordpress/hooks/db-relation-changed)
we don’t do anything special, we create an apache vhost and set it up
for you. While this is simple, there’s no reason we can’t make this
charm be a turbo charged deployment of Wordpress. Let’s look at some of
the recommendations we see on his blog and on HN:

-   A simple caching plugin would have quickly fixed this for you.

-   In my stacks I always use nginx in conjunction with Apache to handle
    as much of the static content load as is possible and that lifts a
    huge weight from Apache. Next up is to always use a bytecode cache
    like [Xcache](http://xcache.lighttpd.net/) or APC, these help give a
    huge boost in performance.

-   But then you hit a wall, next up are limitations in WP SQL and
    MySQL, these can be helped by messing with the queries and using
    Memcached also helps to significantly boost the DB performance here.

-   I had similar nightmares to you for a long time with Apache/PHP/WP,
    then finally put Varnish cache in front of the whole thing.

-   And someone recommends just [shoving the
    thing](https://github.com/mojombo/jekyll/wiki) in Jekyll and
    serving that.

I’m sure everyone will have an opinion on how to deploy Wordpress. From
an Ubuntu perspective, we ship the wordpress and mysql packages, but
that only gets you so far. It’s still up to you to configure it, and as
this guy proves, you can mess something up. Wouldn’t it be nice if we
could collect all the experience from people who are Wordpress
deployment experts, put that in our charms and just give people that out
of the box?

We could use nginx in the Wordpress charm, with FastCGI, we can
certainly add relations to make varnish and memcached know what to do
when they’re related to wordpress. And/or just “juju add-relation jekyll
wordpress” and have that Just Work.

These are the kinds of problems we’re trying to tackle with juju. Will
it be totally perfect for everyone’s deployment? Of course not, that’s
impossible, but we can certainly make Patrick’s experience more
uncommon. People will always argue about the nitnoid implementation
details, but we can make those config options; the point is that we can
share deployment and service maintenance as a whole instead of hoping
people put the lego blocks together in the right order.

Interested in turning a plain boring charm into something sexy? I’ve
filed [the bug here](https://bugs.launchpad.net/charms/+bug/929750), let
us know if you’re interested.

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
