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

Greetings folks,

The Juju Ecosystem team at Canonical (joined remotely by community
members) recently had a developer sprint in beautiful Dillon, Colorado
to Get Things Done(™).

Here are the highlights:

![](http://www.jorgecastro.org/images/jujueco1.jpg)

Automated Charm Testing
-----------------------

Tim Van Steenburgh and Marco Ceppi made a ton of progress with automated
charm testing, here’s the prelim state-of-the-world:

-   <http://reports.vapour.ws/charm-tests>
-   <http://reports.vapour.ws/charm-tests-by-charm>

Jenkins Jobs Fired off: 22

This enabled us to dedicate hours of block time of getting as many of
those red charms to green as possible. The priority for our team over
the next few weeks will be fixing these charms, and of course, gating
new charms via this method, as well as kicking back broken charms to
personal namespaces.

Ben Saller helped out by prototyping “Dockerizing” charm testing so that
developers can test their charms in a fully containerized way. This will
help CI by giving us isolation, density, and reliability.

Charm Tests are now launched from review queue to help gating based on
tests passing.

Thanks to Aaron Bentley for supporting our efforts here!

Review Queue
------------

The Charmers (Marco Ceppi, Charles Butler, and Matt Bruzek) dedicated
time to getting through reviews. The whole team spent time creating
fixes for the automated test results mentioned above. We’re in great
shape to driving this down and not ever letting it get out control again
thanks to our new team review guidelines:
<http://review.juju.solutions/>

The goal was to help submitters and reviews know the where they are at
in a review, and next steps needed.

Here are the numbers:

-   Reviews Performed: 189
-   Commits: 228
-   Charms Promulgated: 10
-   Charms Unpromulgated: 7
-   Lines of Code touched: 34109 (artificially high due to SVG
    icons, heh)
-   Reviews Submitted: 84
-   Energy Drinks: 80

Some new features:

-   Users can now log in with Ubuntu SSO and see what reviews they have
    submitted, and reviewed
-   Ability to query the review system and search/filter reviews based
    on several metrics (http://review.juju.solutions/search)
-   Ability for charmers to fire off an automated test of a charm on
    demand right from the queue. When an MP is done against a charm,
    we’ll now automatically reply to the MP with a link to the
    test results. \\o/
-   You can now “lock” a review when you’re doing one so that the rest
    of the community can see when a review is claimed so we don’t
    duplicate work. (Essential for mass reviews!)
-   Queues divided and separated to highlight priority items and items
    for different teams

CloudFoundry
------------

-   Improving the downloader/packaging story so it’s more reusable
-   Cory Johns developed a pattern for charm helpers for CloudFoundry;
    the CF sub-team feels this will be a useful pattern for
    other charmers. They’re calling it the “charm services framework”,
    expect to hear more from them in the future.
-   We were able to replicate the Juju/Rails Framework deployment of an
    application and compare doing the same thing on CF:
    https://plus.google.com/117270619435440230164/posts/gHgB6k5f7Fv
-   Whit concentrated on tracking changes to Pivotal’s build procedures.

![](http://www.jorgecastro.org/images/jujueco2.jpg)

Charm Developer Workflow
------------------------

This involves two things:

### “The first 30 minutes of Juju”

This primarily involved finding and fixing issues with our user and
developer workflow. This included doing some initial work on what we’re
calling “Landing Pages”, which will be *topic* based landing pages for
different places where people can use Juju, so for example, a “Big Data”
page with specific solutions for that field. We expect to have these for
a bunch of different fields of study.

We have identified the following 5 charms as “flagbearer””: Rails (in
progress), elasticsearch, postgresql, meteor, and chamilo. We consider
these charms to be excellent examples of quality, integration with other
tools, and usage of charm tools. We will be modifying the documentation
to highlight these charms as reference points. All these charms have
tests now, though some might not have landed yet.

### Better tools for Charm Authors:

Ben, Tim, and Whit have a prototype of a fully Dockerized developer
environment that contains all of the local developer tools and all of
the flagbearer charms. The intention is to also provide a fully
bootstrapped local provider. The goal is “test anything in 30 seconds in
a container”.

In addition to this, Adam Israel tackled some of our Vagrant development
stories, that will allow us to provide better Vagrant developer
workflow, thanks to Ben Howard and his team for helping us get these
features in our boxes.

We expect both the Docker-based and Vagrant-based approaches to
eventually converge. Having both now gives us a nice “spread” to cover
developers on multiple operating systems with tools they’re familiar
with.

Big Data
--------

Amir/Chuck worked on the following things:

-   Upgrading the ELK stack for Trusty
-   Planning out new Landing Pages focused on the Big Data story
-   Bringing up existing Big Data (Hortonworks) Stack to Charm Store
    standards for Trusty, and getting those charms merged
-   Pre-planning for next phase of Big Data Workloads (MapR,
    Apache distributions)

Other
-----

-   General familiarity training with MAAS, OpenStack on OBs and NUCs.
-   Very fast firehose drinking for new team members, Adam Israel,
    Randall Ross, and Kevin Monroe have joined the team.
-   Special Thanks to Jose Antonio Rey, Sebas, and Josh Strobl, for
    joining us to help get reviews and fixes in the store
    and documentation.
-   We have a new team blog at: <http://juju-solutions.github.io/>
    (Beta, thanks Whit.)
-   Most of the topics here had corresponding fixes/updates to the
    Juju documentation.

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
