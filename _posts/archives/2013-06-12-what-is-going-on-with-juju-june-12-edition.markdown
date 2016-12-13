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

-   [Video recording](http://youtu.be/0qaxWHnqxNQ)
-   [Pad](http://pad.ubuntu.com/7mf2jvKXNa)
-   [Status
    Board](https://trello.com/board/charmers-board/4ec1696da3f94bd2ea5b2b01)
-   [Juju.u.c Meeting
    Site](https://juju.ubuntu.com/community/weekly-charm-meeting/)

Charm Tools
-----------

-   Similar to last week, no real big changes, Marco will hit these
    after he’s done with testing.
-   We need to update the review queue charm schools, the website queue
    fixed the “time to first response”, but the CLI tool is behind. Mims
    to bust it out.

Charm Helpers
-------------

-   adam\_g landing some fixes to charm helpers.
    -   openstack utility fixes
    -   improve test coverage
    -   jamespage added some intelligent restarting bits and some reorg
        too, thanks -server team!
-   Wedgewood stops by to provide an update
    -   Most items in contrib have been moved to the library, it’s
        shaping up!
    -   Nick Moffit is working on the CLI to helpers, making it
        available to all languages
-   If you find yourself doing things over and over again, talk to them
    and file feature bugs!

Testing
-------

-   plugins good to go - more changes to land due to feedback from the
    GUI team.
    -   GUI team dogfooding this harness and plugin, thanks guys!
-   harness
    -   End of month target for all of this to land. June 28th!
    -   Mims to blog about the framework/harness, part 1 almost done.

Docs
----

-   now live at <https://launchpad.net/juju-core/docs>
    -   Yes, we’re moving docs back into core so we can version along
        with core. I know right.
-   Anyone can contribute branches, even Jorge did, and he’s not smart,
    you are out of excuses!
-   Jade templates are kind of tempermental formatting wise, Nick
    investigating dropping them and doing pure HTML to lower the barrier
    to entry.
    -   investigate how we proceede with Jade post the navigation
        settling being defined.
-   Nick thinks we can go live now
    -   What do we need to go live?
-   videos ongoing, assigned out upgradees and destroying services
-   todos:
    -   link mapping (marco)
    -   versioning (nick)
    -   where to host old and new docs (arosales to follow up RT
        with IS).
    -   decide how to handle getting started docs on
        juju.ubuntu.com (jorge)
-   Next action: evilnick to bring old user author docs by June 17
    -   arosales will open RT
-   Looking to have docs complete by June 28.

Charm Framework updates
-----------------------

-   Rails/Rack unblocked via Antonio, we should have work landing soon!
-   no updates on node.js from jeff/mims, but Joynet is interested in
    checking them out and contributing.
    -   Part 2 of the charm school this Friday will be node again.
-   Mims would like to see preinstallation of packages, is now
    considering this a blocker for platforms charms.
    -   Framework communities will want these.
    -   Jorge/Antonio to bring this up with core team. Here’s [the
        bug](https://bugs.launchpad.net/juju/+bug/1190293).
    -   need a tag in juju-core bugs to show user-feedback/contribution
        growth
    -   New charm! Liferay! Needs a second round of review.

Events
------

-   OSCON - People need to rate/categorize charms, \~charmers!!
    -   need charms to have ratings, icons, and categories
-   Strata still pending.
-   Mims still in progress for his epic data plumbing talk at Stanford.

Blockers on Trello
------------------

-   Backports of goju to 12.04
    -   Still in progress

Goals for upcoming week
-----------------------

-   Mims: 0mq and storm
-   mims preping for Stanford talk
-   evilnick working on moving charm author docs content over
-   arosales finding a hosting place
-   arosales move docs to new branch
-   marco working on next iteration of testing harness
-   jorge,arosales to follow on on pre-install hooks with juju-core
-   Everyone: Work on docs!!
-   Everyone: When you touch a charm, rate it, categorize it, see if you
    can give it an icon.
-   Do your docs videos!

Misc
----

-   [Charm icon
    guidelines](https://docs.google.com/document/d/1hBTH_7RLUYMV-VhZOGxb-bFHICXyVRU4t8L79Dlea80/pub)

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
