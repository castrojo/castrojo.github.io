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

One of the things I’ve heard about people managing services over the
last year or so is that even though it’s useful to do things at the
service level, sometimes even doing that can be time consuming or
tedious.

For example if you want Discourse or Mediawiki then you need to know
which databases those services need. Why not just steal what some other
person has put together and deploy it all at once? Services by
themselves are fun but I want an entire working thing out of the box!

![](http://www.jorgecastro.org/images/bundles.png)

Bundles are sets of services that are bundled together in one file that
you can deploy. And we’re putting them in the Juju Charm Store so that
you not only get to share individual services, but clumps of working
deployments. It’s easy, you merely model your deployment in the [Juju
GUI](http://jujucharms.com), export, and then share the yaml file.
Bundles also have [their own
page](https://jujucharms.com/fullscreen/search/bundle/~makyo/mediawiki-scalable/5/mediawiki-scalable/?text=mediawiki-scalable#bws-bundle)
in the store, showing users what components are available, how to use
it, and what they consist of.

The nice thing is that you can deploy the entire thing *at once*:

    juju quickstart bundle:~gary/demo/2/instantBigDataNoSQL

![](http://www.jorgecastro.org/images/bundles2.png)

This fires up a bootstrap node, add the Juju GUI to the environment and
deploys this monster.

Here’s what it looks like from scratch.

    sudo add-apt-repository ppa:juju/stable
    sudo apt-get install juju-core juju-quickstart
    sudo apt-get update

    juju init -w

Then edit `~/.juju/environments.yaml` with your cloud credentials. Then
pick a bundle to deploy.

    juju quickstart bundle:~makyo/mediawiki-scalable/5/mediawiki-scalable

or

    juju quickstart bundle:~jorge/mediawiki-simple/3/mediawiki-simple

or

    juju quickstart bundle:~jorge/discourse/5/discourse-simple

Bundles are in beta, so here’s the caveats. Doing the
`environments.yaml` dance gets tedious, so we’re working on the
quickstart command to prompt you for credentials for whatever cloud you
want to use. We also realize that the URLs aren’t exactly ideal, but
we’re working to make that simpler. Bundles don’t support –to right now
either, so “run an entire Discourse install on one cheap node” is not
quite there yet, but we’ll be there soon. The goal by 14.04 is just to
have the one quickstart command do what you want without all the
previous mumbojumbo.

jujucharms.com will continue to grow support for bundles, right now it’s
mostly focused on charms, and while charms are great and an important
building block we’ll be pushing bundles as a complete solution for a
deployment. As far as submitting your bundles to the charm store, the
process is slightly different than charms, we’ll be pushing updated
documentation on how to do this over the next few days. In the meantime
feel free to deploy these example ones.

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
