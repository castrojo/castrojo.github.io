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

Juju Charm Ecosystem Status for the 30th of October
===================================================

General Info
------------

-   [Pad](http://pad.ubuntu.com/7mf2jvKXNa)
-   [Status
    Board](https://trello.com/board/charmers-board/4ec1696da3f94bd2ea5b2b01)
-   [Juju.u.c Meeting
    Site](https://juju.ubuntu.com/community/weekly-charm-meeting/)
-   [Video of Meeting](http://youtu.be/HnNwRUAgyow)

Highlights
----------

-   Bundles are coming!
-   13.10 is out! New cycle planning begins! Check out the blueprints:
    <https://blueprints.launchpad.net/sprints/cloud-oct-2013>
-   We need to resubmit them to UDS if appropriate:
    <https://blueprints.launchpad.net/sprints/uds-1311>
-   1.16.1 point release coming out this week!
-   The “null” provider is now the ssh provider, and shall be forever
    known as the ssh provider. All mentions of “null” provider shall be
    stricken from the record as soon as it lands. We’ve always been at
    war with Eastasia.

Tools
-----

-   1.1 release coming tomorrow with support for bundles.
-   Minor bug fixes
-   Charm testing template included to create boilerplate Amulet tests.

Helpers
-------

-   no changes, tons of discussion, please join UDS for the details,
    here’s high level view:
    -   Packaging for charm helpers, so you don’t have to embed them
        anymore
    -   Multiple language support in charm helpers!

Amulet
------

-   No changes, there will be more coming based on user feedback, no
    release date set yet.

Docs
----

-   More work in the charm author docs specifically.
-   Documenting the interfaces is coming
-   config pages getting updated to reflect 1.16.
    -   Would also like to rework some of the screenshots (HP Cloud
        changed again).

Charm Updates
-------------

-   http://manage.jujucharms.com/recently-changed
-   Queue @ http://manage.jujucharms.com/tools/review-queue
-   CONTEST OVER! Judging has begun.
-   Owncloud has critical fix in the charm queue, needs to get in asap.

-   Lots of progress clearning it out over the past 2 weeks, we’re
    almost out of the hole.

Bundles
-------

What is a bundle?

-   Jorge: Bundles are to charms as metapackages are to packages
-   Marco: But you can define bundles of bundles, so it’s more like a
    bundle is a source package of a package that has multiple binaries.
-   Ok enough with the analogies, bundles are sets of charms AND
    relations that represent a workload, you deploy that into your cloud
    so like.
-   You can export a bundle from your GUI by hitting shift-d, and then
    share with others
-   You’ll be able to share you bundle with the community, it’s just a
    simple yaml file.
-   `charm tools` will lint your bundle!
-   How do we promulgate official bundles?
-   TODO for UDS, we need a session on Bundle policy.

Events
------

-   http://juju.ubuntu.com/events
-   ODS HongKong (Nov 5-8)
-   LISA’13 (Nov 4) (GlusterFS community days)
-   SCaLE CFP - 15 December
-   RubyConf (Nov 8-10)
-   AWS re:Invent (Nov 12-15)
-   MongoSV (Beginning of Dec, TBD)
-   Charm School schedule will be updated wih the t-cycle

Charm Championship
------------------

-   Submissions are in … judging has begun!
-   Announcement TBD.

GOALS
-----

-   \[jorge\] Openstack bundle deployment thing from jamespage:
    SUPERCEDED
    -   Cloud installer + we’ll make other bundles for the GUI
-   \[m\_3\] mapR charm review: INPROGRESS
-   \[marco\] Get 1.0(.1) charm-tools into precise: BLOCKED
-   \[marcoceppi\] Document SimpleStreams, scrub docs to make sure
    public-bucket-url and friends are updated: INPROGRESS
-   \[jorge\] - Local provider troubleshooting: DONE
-   \[marcoceppi\] - Document local provider troubleshooting: INPROGRESS
-   \[jorge\] - Document local provider troubleshooting: INPROGRESS
-   \[nickveitch\] - File a bug to bring -v back (show-log? really?):
    DONE
-   \[nickveitch\] - Document tags in the MAAS provider: DONE
-   \[nickveitch\] - control-bucket is now chosen automatically if
    omitted from the configuration for new ec2 and openstack
    environments.: DONE
-   \[nickveitch\] - admin-secret is now chosen automatically if omitted
    from the configuration of a new environment.: DONE
-   \[jorge\] \[nickveitch\] - Create a logging page. Logging
    has changed. You can specify an environment variable
    “JUJU\_LOGGING\_CONFIG”, or you can specify –log-config on the
    command line. To show the log on the command line, now
    use –show-log. The –debug has been kept to be short-hand for
    “–log-config==DEBUG –show-log”, and –verbose has been deprecated
    with its current meaning.: TODO
-   \[marcoceppi\] Document charmhelper http relations: TODO
-   \[marcoceppi\] Documenting the \~charmers responsibilities:
    INPROGRESS

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
