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

The [way to run WordPress in the
cloud](http://www.jorgecastro.org/2012/08/31/the-way-to-run-wordpress-in-the-cloud/)
got better last week as Marco Ceppi continues to add improvements to the
[WordPress Juju Charm](http://jujucharms.com/charms/precise/wordpress).

First off is the new [WordPress
3.5](http://wordpress.org/news/2012/12/elvin/), which has been available
to Juju users since it was released with a simple
`juju upgrade-charm wordpress`. Nice.

For this week Marco’s added some options for the kind of webserver used
in the charm. Out of the box we’ve been using nginx, which is great, but
some organizations prefer using things that are more known to them, and
since Apache is available in Ubuntu’s main repository and supported for
5 years, why not have the option? So now you can switch the webserver
with the following command:

    juju set wordpress engine=apache2

And your deployment will reconfigure itself to server with Apache instad
of nginx. You still get the nice auto load balancing (without the need
for a proxy instance), but you lose some memcached integration (see the
[README](http://jujucharms.com/charms/precise/wordpress) for more).
Ready to switch back?

    juju set wordpress engine=nginx 

You can just switch back and forth if you’d like, it’s kind of cool to
run the command, wait a few minutes, and hit F5 in your browser to see
it switch back and forth. For those of you watching/hoping for nginx to
be included in Ubuntu’s main repository, you can [follow this
blueprint](https://blueprints.launchpad.net/ubuntu/+spec/servercloud-r-webscale).
Enjoy!

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
