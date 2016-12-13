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

aka. Holiday Leftovers {#aka-holiday-leftovers}
----------------------

Time for another Unity status report. As you can expect due to holidays
around the world not much progress was made other than expanding our
waistlines.

Expect a flurry of activity this week as Unity developers spin up for
the new year. Next week the Unity team will be sprinting in Dallas,
Texas along with other members of the Canonical Platform team so expect
a bunch of updates.

New to Unity but not Ubuntu is Shane Fagan, who [adds a unity
–replace](https://bugs.launchpad.net/ubuntu/+source/unity/+bug/692569)
command. Hey, it’s all about the little things. Matthew Rasmus returns
with 2 fixes (both committed in trunk but not yet released, expect it on
Thursday/Friday):

-   [691765](https://bugs.launchpad.net/unity/+bug/691765) - When a menu
    is triggered from Alt+key, app name stays visible on panel 

-   [691812](https://launchpad.net/bugs/691812) - Window border doesn’t
    get restored

-   Stefano Candori has made progress on [getting quick
    lists](https://bugs.launchpad.net/unity/+bug/688407) connected up to
    the Trash Can. 

-   Mathieu Trudel’s been looking at fixing the top panel’s
    [multimonitor
    awareness](https://bugs.launchpad.net/unity/+bug/675862). 

The Big List
------------

Lots of repeats here due to work stoppage, now is the time to jump in if
you want a piece!

-   [684193](https://bugs.launchpad.net/unity/+bug/684193) - compiz
    crashed with SIGSEGV in g\_source\_unref()

-   [683547](https://bugs.launchpad.net/unity/+bug/683547) - Bottom
    launchers hard to expand with filled launcher bar, need edge
    scrolling

-   [687956](https://bugs.launchpad.net/unity/+bug/687956) - should
    display the launcher tooltips after a delay

-   [687958](https://bugs.launchpad.net/unity/+bug/687958) - should
    provide an IsUnityRunning() dbus method

-   [688816](https://bugs.launchpad.net/unity/+bug/688816) - Don’t
    create windows over the panel

-   [689929](https://bugs.launchpad.net/unity/+bug/689929) - Update
    managers Apply Settings window doesn’t trigger unity’s smarthide

-   [691114](https://bugs.launchpad.net/unity/+bug/691114) - Quicklists
    for icons at the bottom of the screen are clipped by screen edge

-   [677594](https://bugs.launchpad.net/unity/+bug/677594) - Workspace
    switcher useless with one workspace

-   [681428](https://bugs.launchpad.net/unity/+bug/681428) - scrolling
    does not work on the sound menu

-   [686182](https://bugs.launchpad.net/unity/+bug/686182) - Unity
    launchers run multiple copies of program if clicked multiple times
    before the program loads

-   [688537](https://bugs.launchpad.net/unity/+bug/688537) - Launcher
    icon tooltip not following system font update

-   [689010](https://bugs.launchpad.net/unity/+bug/689010) - wrong icon
    for “blank cd-r disc” in launcher

-   [692967](https://bugs.launchpad.net/unity/+bug/692967) - First-run
    of Unity should scan AWN, Docky and other popular launcher settings

-   [600875](https://bugs.launchpad.net/unity/+bug/600875) - No
    documentation for using/configuring Unity

-   [692444](https://bugs.launchpad.net/unity/+bug/692444) - clicking
    trash multiple times opens multiple instances of it.

-   [693792](https://bugs.launchpad.net/unity/+bug/693792) - Launcher
    icon goes behind launcher if dialog pops up while dragging icon

Here’s [the full list](http://goo.gl/i1WA1).

Other Unity Work
----------------

-   Mathieu Trudel continues to work on the nm-applet port to
    application indicators. He’s now got wireless icons in the dropdown.
    (This is a screenshot of it from his laptop, so this is just a
    tease, nothing landing yet) 

![](http://media.tumblr.com/tumblr_leienga0OT1qb5bmy.png)

-   Conor Curran has sent [along an
    update](http://castrojo.tumblr.com/post/2420040342/sound-indicator-news-and-updates)
    on what’s going on with the sound indicator

-   Auto/intellihide is now on by default in trunk and intial support
    for using the Super key to invoke the launcher has also landed.

-   The launcher now supports scroll events (like your mouse wheel).

**Getting Involved**
--------------------

Instructions for getting started are [available
here](http://unity.ubuntu.com/getinvolved/%20).

For more information check out the wiki
page:[\[https://wiki.ubuntu.com/Unity/Bitesize\](https://wiki.ubuntu.com/Unity/Bitesize)](http://goo.gl/tiheb)

If you have any questions feel free to pop by
on [\#ayatana](http://webchat.freenode.net/?channels=#ayatana) on
Freenode.

</div>

<div class="share">

<div class="addthis_toolbox addthis_default_style">

[](){.addthis_button_tweet} [](){.addthis_button_google_plusone}
[](){.addthis_counter .addthis_pill_style}

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
