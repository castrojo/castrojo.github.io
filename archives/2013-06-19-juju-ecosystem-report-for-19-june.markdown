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

-   [Video recording](http://youtu.be/RzEK10bC58w)
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

Ben’s charm-tools feedback. Just some ideas:

-   It would be nice for `charm create` to work more like `dh_make`
-   It should ask for the license to use, and populate the copyright
    file
-   It would be nice for it read the DEBFULLNAME and DEBEMAIL and
    s/DEB/CHARM/ environment settings or even .bzr information to
    determine authorship
-   Category should be asked during the charm create
-   It should initialize the branch and accept `--git` or `--subversion`
-   It should ask for standard requires, i.e. allow
    `--requires-db mysql` or `--requires-http varnish` or prompt
-   It should ask for what it provides, i.e. `--provides http`
-   It should offer the option of a `--peer` for peer relationships
-   For the relationship hook, it would be great to have commented
    examples based on the `--requires-X`

Charm Helpers
-------------

-   MPs coming in, progress looks great.
-   Wedgewood handling incoming work, activity happening, Marco will
    roll up a summary of work for next week.
-   Thanks Matthew for driving this!

Testing
-------

### Minor work:

-   charmtester updates to make it more flexible. This is the one that
    reports to jenkins on qa.ubuntu.com
-   juju test plugin, new features requested by the gui team
    -   Can now run in an existing bootstrapped environment
    -   You can now specify a config file in the test directory with
        options for the tests you want to run. There’s an example yaml
        template if you run `juju-test -h` if you wanna check it out,
        will be published EOD 2013-06-19

### Major work:

-   First release of the testing harness (lp:amulet) ready (ppa being
    prepped for folks to use). \\o/
    -   Wait command, just like `jitsu watch`
    -   Deployer command, describe an environment setting by running a
        bunch of manual commands, and then uses Kapil, Adam, Matthew, &
        Co lp:juju-deployer tool to stand up an environment in a test.
        “Whoa”.
        -   We’re using it to test openstack deployments and it’s
            designed to set up complex environments that are repeatable.

Docs
----

-   Translating old charm author docs to the new format.
    -   DONE AS OF MONDAY. \\o/ \\o/ \\o/
    -   Just need to finish up the testing, and validation (just a port
        over of old docs to the new format, content still needs to
        be confirmed).
    -   idea - have the new docs deployed as a sub off the
        apache2 charm. Have the charm do a cron to update from the bzr
        branch every 12 hours (need feedback).
    -   Redirects are ready, for when docs go live
    -   New doc branch @ lp:\~charmers/juju-core/docs
    -   any docs problems - [file a
        bug](https://bugs.launchpad.net/juju-core/docs)!

Charm Updates from the Store
----------------------------

-   <http://jujucharms.com/recently-changed>
-   Jorge talking to MariaDB see if someone is interested in adding
    Maria Support to the MySQL charm, any help here appreciated, if
    you’re using MariaDB and Ubuntu we could use a hand here!

Misc
----

-   Merge proposal workflow.

Events
------

-   OSCON - In progress, no issues.

FRAMEWORK UPDATES
-----------------

-   Rails - almost ready to begin
-   node.js - in progress.
-   Django and friends - in progress, no thanks to our messed up
    merge proposals. :)

Blockers
--------

-   Backports of juju-core to 12.04!!
    -   Dependencies on go compiler, core team aware of it, trying
        to resolve.
    -   charm tools and helpers backports blocking on this too.

Goals from last week
--------------------

-   Mims: 0mq and storm
-   mims preping for Stanford talk
-   Do your docs videos!

Goals for this week
-------------------

-   Mims to sync with Dave on juju-core pre-install hooks.
-   Mims: 0mq and storm
-   Mims preping for Stanford talk
-   Everyone: When you touch a charm, rate it, categorize it, see if you
    can give it an icon.
-   Do your docs videos!
-   People who did not do docs/videos this week and need to be
    embarrassed
    -   Jorge Castro
    -   Antonio Rosales
    -   Mark Mims
    -   Marco Ceppi
-   arosales: get docs to a charm’ed up deployed stage
-   utlemming: on vacation
-   jorge: video and doc page
-   marco: vacation
-   mims: Storm and 0mq, talk prep
-   nick: 4 videos

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
