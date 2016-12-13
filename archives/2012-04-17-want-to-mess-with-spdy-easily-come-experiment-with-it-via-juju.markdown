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

(This is half broken and not ready, but it’s too cool to not tell you
about right away.)

The folks over at Google released a [new snapshot of
mod\_spdy](http://googledevelopers.blogspot.com/2012/04/add-spdy-support-to-your-apache-server.html)
for use with Apache.

Thinking this would be a cool way to show off juju’s subordinate
feature, Clint Byrum got to work and hacked together a mod\_spdy
subordinate charm; which means (assuming it works), that we can just
tack it onto things serving via Apache and get mod\_spdy relatively easy
for all the charms that would use it in the store. Neat huh?

Here it is:

<http://jujucharms.com/~clint-fewbar/precise/mod-spdy>

And here’s how you’d test it:

    juju deploy wordpress
    juju deploy mysql
    juju add-relation mysql wordpress
    juju expose wordpress
    juju deploy cs:~clint-fewbar/precise/mod-spdy
    juju add-relation mod-spdy wordpress

Clint realized that juju does not allow subordinates to open ports for
their primaries, so you have to use the `open-port` script in
juju-jitsu.

To do that, after you’ve done the steps above:

    bzr branch lp:juju-jitsu
    juju-jitsu/sub-commands/open-port your-primary-service 443

https://your-public-ip/ should be SSL, and should be using SPDY if you
try it in Chrome/Chromium/Firefox.

This is a rough cut, and not in the charm store yet for obvious reasons,
and when I tested it it didn’t even serve the right page, but, at least
the error was served over SPDY, heh. But you can immediately see that by
using a subordinate charm you can add on a feature to an existing charm,
making it a nice way to test something new and shiny.

We’re in \#juju on freenode if you want to start whacking on this and
making it more deployable, find bugs, and finish the implementation, we
can then make this a nice option for Ubuntu Server users. Happy spdying!

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
