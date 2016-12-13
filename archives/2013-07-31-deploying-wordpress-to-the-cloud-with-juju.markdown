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

I’ve talked in the past about [The Way to Run Wordpress in the
Cloud](http://www.jorgecastro.org/2012/08/31/the-way-to-run-wordpress-in-the-cloud/).
It looked like this:

    juju deploy wordpress
    juju deploy mysql
    juju add-relation wordpress mysql
    juju expose wordpress

But the problem with building tools that scale up is that we sometimes
forget that people like to *scale down* too. Counting the bootstrap node
that comes out to 3 instances. We default to m1.smalls so that comes out
to about about \$133 a month for an on-demand WordPress blog. Not very
cost effective.

As of Juju 1.11.3 and newer, we can now *deploy services to the same
instance*. How we express this is via the `juju deploy --to` command.
Let’s look at our WordPress example again, this time, let’s save some
money and run the entire thing on one node.

    juju bootstrap
    juju deploy --to 0 wordpress
    juju deploy --to 0 mysql
    juju add-relation wordpress mysql
    juju expose wordpress

Then run a quick `juju status` to get the public IP of your WordPress
installation, and you’re done. On reserved instances that comes down to
\$61 a year, or \$5.08 a month! Commit to three years on AWS and it’s
closer to \$2.65 a month. Now we’re talking, just don’t forget to add
the cost of bandwidth in there.

So what’s the big deal? Running these things on one instance isn’t
exactly rocket science. Well ok. Your twitter moment has arrived and now
you need to scale your blog. You need on-demand scalability:

     juju add-unit wordpress

Without the `--to` juju fires up a new instance of wordpress to help you
scale. How famous is your new blog post? `juju add-unit -n4 wordpress`
will fire up another 4. Now let’s scale back down, let’s remove units 3
and 4:

    juju remove-unit wordpress/4
    juju remove-unit wordpress/3

This brings us down back to nodes 0, 1, and 2 running. Keep on going
until you’re back to just node 0 running everything. Start on one
instance and be able to scale up and down based on traffic. Not bad
indeed!

You’re not just getting some out of the box vanilla WordPress and MySQL
either. You’re getting a battle-hardened scalable [WordPress
deployment](https://jujucharms.com/precise/wordpress-HEAD/#bws-readme)
that’s tuned to scale with nginx. If you want to turn the crank to 11
you can also deploy memcached with it for a really fast blog.

Some caveats; while this works with WordPress right now the individual
charms are running on the raw instance, they are NOT in containers yet!
That is, if you deploy multiple charms to one box they might collide and
stomp on each other. So play with it, but I recommend waiting until the
next release of Juju (next month) for containers to land so we have a
nice clean seperation of the units on the instance. Work on that
continues, along with adding this ability to the GUI. However WordPress
works today!

In the meantime here’s how to [Get
Started](https://juju.ubuntu.com/docs/getting-started.html) with Juju.
Happy Orchestrating!

References:

-   [Targetted Machine Deployment with
    Juju](http://javacruft.wordpress.com/2013/07/25/juju-put-it-there-please/)
    by James Page

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
