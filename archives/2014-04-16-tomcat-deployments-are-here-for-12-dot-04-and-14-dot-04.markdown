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

We’ve been trying to get our Java developer story in order, as it’s one
of the areas where users have been telling us they’d like to see made
easier to manage. We brought Matthew Bruzek on board, who will be
focusing on our Java framework stuff.

Here’s his first cut, and it’s a big one. We now finally have an all
emcompassing [Apache Tomcat
Charm](http://manage.jujucharms.com/charms/precise/tomcat). This charm
allows you to develop your app on top of it as a subordinate charm and
be able to deploy it. As an example, let’s deploy
[OpenMRS](http://openmrs.org/).

    juju deploy tomcat7
    juju deploy openmrs
    juju deploy mysql
    juju add-relation openmrs mysql
    juju add-relation openmrs tomcat7
    juju expose tomcat7

The magic happens when you relate openmrs to tomcat7, that installs
OpenMRS in Tomcat, and then you’re good to go.

The charm contains [a ton of
options](https://jujucharms.com/precise/tomcat/#configuration) for you
to check out, including deploying to Tomcat6 if that’s how you roll.

Those of you looking for “just shove my war file out there” can check
out Robert Ayre’s
[j2ee-deployer](http://manage.jujucharms.com/~robert-ayres/precise/j2ee-deployer)
charm. Here’s [a blog
post](http://voices.canonical.com/robert.ayres/2012/08/01/juju-java-cluster-part-1/)
on how to use it.

That one is not in the charm store yet, but we’ll get to it!

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
