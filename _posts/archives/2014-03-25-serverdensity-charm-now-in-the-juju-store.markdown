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

Some good news for monitoring SaaS Fans,
[ServerDensity](http://www.serverdensity.com/) is now in the [Juju Charm
Store](http://jujucharms.com/precise/serverdensity). This means that the
ServerDensity agent is now available to tack onto any deployed service
in your environment. We call this kind of charm a *subordinate*, here’s
how you’d use it.

Let’s deploy a MongoDB Cluster:

    juju-quickstart bundle:mongodb/cluster

This is a 13 node cluster, let’s add some monitoring! First we’ll deploy
serverdensity, and then the crucial step, relating serverdensity to the
*service*:

    juju deploy serverdensity
    juju add-relation mongos serverdensity

Now let’s tell ServerDensity that we want it to monitor Mongo and we
need an API key since it’s a service that needs a key:

    juju set serverdensity agentkey="Keyfromyourserverdensitycontrolpanel"
    juju set serverdensity mongodb-server="ip of mongos node"
    juju set serverdensity mongodb-dbstats=true

Now, why do I need to give it the ip of mongo’s node? Well, as v1 of
this charm we’re setting this manually, but what we could do in the
future is take care of those settings as soon as the relationship is
made instead of making the user set those config values. But hey, why
nitpick, monitoring a MongoDB cluster with 5 commands isn’t a bad place
to start!

There are a bunch of [configuration
options](https://jujucharms.com/sidebar/search/precise/serverdensity-0/?text=serverdensity#configuration)
for you to play with for service monitoring with Apache, MySQL, and
RabbitMQ. When used standalone the charm will just do machine monitoring
for whatever you related it to.

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
