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

We had alienth from Reddit hanging out during one of the Ubuntu Global
Jams and he took a moment to hang out with us in \#juju and tell us a
little bit about how they deploy Reddit.

I started with the [Reddit Installation
instructions](https://github.com/reddit/reddit/wiki/Install-guide) and
found out some of the technology they use. Postgres, Cassandra, Rabbit,
and memcached. Hey, we just so happen to have [charms for
those](http://charms.kapilt.com/charms) services.

Then I learned that they have an [install
script](https://gist.github.com/922144) that installs reddit. Well, if
this was charmed up we could do:

    juju bootstrap
    juju deploy reddit
    juju deploy postgres
    juju deploy cassandra
    juju deploy memcached
    juju deploy rabbitmq

Then relate them all to reddit, the hooks in the charm would then do
what the installation instructions say for each service:

    juju add-relation reddit postgres
    juju add-relation reddit cassandra
    juju add-relation reddit memcached
    juju add-relation reddit rabbitmq

And then after all the instances have fired up you can just
`juju expose reddit`, which opens up the port, and then you just hit up
the URL.

This would be an awesome charm for a bunch of reasons. First, we have
existing charms for everything they need already, the magic would be in
how to relate the services to the reddit charm. Theoretically we could
`juju add-unit cassandra` and that would just work. We’d need to test it
to find out.

The other bit that is interesting is that if you see [the
comments](https://gist.github.com/922144) in the script people are
having small problems getting it to work. Things like “the script uses
aptitude and that no longer works.” Well, if this was a charm it would
just live in the juju charm store, where people can fix it (like they
are already doing on github). But the difference between living in a
github gist and the charm store is that we continuously automatically
check every charm so we *know* it works, and it’s easily findable by any
Ubuntu server user.

To me that is the best part about juju. Take our convenience scripts off
of pastebins and into a place where we can keep them updated, tested,
and deployable for everyone. I am hoping that someone takes Reddit and
submits it into the [juju Charm
Contest](https://juju.ubuntu.com/CharmContest) so that we can make it
rock.

Any takers? We’ve got a mirror of our [charms on
github](http://github.com/charms) if you want to take the gist and start
charming it up. Here’s how you can [get
started](https://juju.ubuntu.com/Charms) if you are interested.

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
