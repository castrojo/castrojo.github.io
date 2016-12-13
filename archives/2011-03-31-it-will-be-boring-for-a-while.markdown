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

(but in a good way)

([Original
Post](http://www.omgubuntu.co.uk/2011/03/unity-bitesize-bug-status-for-29-march/))

While there is no exciting new bling to talk about this week, there are
plenty of bugfixes to be had for this Unity release.﻿﻿ This week the
team welcomes Nico van der Walt as he makes his introduction fixing Bug
[\#731212](https://bugs.launchpad.net/unity/+bug/731212): “Applications”
and “Files & Folders” keyboard shortcut overlays not  drawn correctly
with scalable launcher and Bug
[\#741346](https://bugs.launchpad.net/unity/+bug/741346): superkey
shortcut labels does not scale properly.

[![](http://www.omgubuntu.co.uk/wp-content/uploads/2011/03/nic-150x150.jpg)](http://www.omgubuntu.co.uk/wp-content/uploads/2011/03/nic.jpg)

*“The Ubuntu community is a big inspiration for me and I love how
friendly everyone is. Unity will be a big success and I look forward to
being a part of this great Linux distribution.”*

Also this week we have Andreas Richel submitting his first fix for
implementing a more robust method of launching applications from the
home view (lp:730623). Unfortunately his camera is broken so no picture,
but he sends along *“I’m a 20-year-old German computer science student
in my 6th semester. I’ve been passively following Ubuntu and the bug
trackers for some time now, but was unable to find enough time to dig
into an ongoing open source project. So this really is a first for me
:)”*

Also back this week are veterans Marco Biscaro and Andrea Azzarone,
fixing Bug [\#742985](https://bugs.launchpad.net/unity/+bug/742985)
‘Lenses with no shortcut still display black box when pressing super
key’ and Bug [\#741775](https://bugs.launchpad.net/unity/+bug/741775)
‘Launcher icon progress-bar too big for a 32px launcher’. These two are
like clocks, something landing almost every week!

Wait, more Bugs?
----------------

This week [the
list](https://bugs.launchpad.net/unity/+bugs?field.tag=bitesize) is up
to 39 bugs, a new high. Now you might be thinking “Wait a minute, I
thought all these brilliant people were doing awesome, how can the list
of bugs go UP!?!” As it turns out, there have been about 50 bitesize
bugs fixed so far (the green line):

[![](http://www.omgubuntu.co.uk/wp-content/uploads/2011/03/Selection_049-500x374.png)](http://www.omgubuntu.co.uk/wp-content/uploads/2011/03/Selection_049.png)

What happens is at the beginning the bugs aren’t really bitesize since a
bunch of plumbing work is going on. Towards the tail end as we get
towards the polishing phase it’s easier to nick off and fix bitesize
bugs, especially as more and more people are able to run it the closer
you get to the Beta milestone. If anything, the list of bitesize bugs
will probably continue to grow, especially when Unity goes into another
feature phase after Natty. However as you can see the green “Fix
Released” line, the number of bugs being fixed also goes up as the code
matures and is exposed to more people who want to hack on it. The slow
march towards progress continues.

### Other Unity Updates

(from the [Desktop Team
Report](https://wiki.ubuntu.com/DesktopTeam/Meeting/2011-03-29))

-   As usual, Unity (and related components) released last Thursday,
    ready for beta (3.6.8) + some bug fixes cherry-picked crash fixes
    for the beta freeze.

-   This week, we got, in addition to a lot of bug fixes:

    -   Multitouch full support handling. If you didn’t test it and you
        have a supported hardware, you should probably give it a try,
        the handles (that you can [activate by ccsm and a
        keybinding](http://askubuntu.com/questions/31877/how-do-i-turn-on-unity-drag-handles))
        are just… gorgeous!

    -   Introduction of a pending waiting for approval “fade and slide”
        effect when hovering the bfb (in experimental plugin settings)
        that may be set by default.

    -   Some keynav better handling in both the launcher and the dash,
        as well as Quicklist having now the title name in the Quicklist
        (as in maverick)

    -   Launcher now responds to theme change!

    -   Under the cover, a rewrite of the Hide behavior machine enabling
        more effective automated tests.

-   New Zeigeist synced with debian to get in sync with the latest
    debian stack

-   Some new compiz uploads to fix miscellanous issues, like more
    invisible window fixes, Alt + Tab fixes, some redrawing issues and
    autorespawn on crash

For people found of the full story, the now classic
link: [\[https://launchpad.net/unity/3.0/3.6.8\](https://launchpad.net/unity/3.0/3.6.8)](https://launchpad.net/unity/3.0/3.6.8)

How to Get Involved
-------------------

### 1. Get the Code

Follow the [Step by Step
Instructions](http://unity.ubuntu.com/getinvolved/) and [Wiki
Page](https://wiki.ubuntu.com/Unity/Bitesize). This will get the code
from Launchpad, set up your development environment, and getting you
used to the Launchpad workflow.

### 2. Pick a bug

Here’s the [full list](http://goo.gl/tiheb) if you want to find more,
feel free to just grab one, assign it to yourself, mark it in progress
and get started.

### 3. Fix your bug and then get your code into Unity

Don’t worry we won’t leave you hanging, you can get a-hold of a Unity
developer through many different ways:

-   ayatana on freenode IRC during European and American workdays. Or you can post to [the mailing list](https://launchpad.net/~ayatana-dev) if you have a question. {#ayatana-on-freenode-irc-during-european-and-american-workdays-or-you-can-post-tothe-mailing-listhttpslaunchpadnetayatana-dev-if-you-have-a-question}
    ================================================================================================================================================================

-   We also have weekly IRC Q+A for any developer who wants to dive in
    and ask a Unity developer. 7pm-8pm UTC (That’s 2pm EST) every
    Friday!

*Remember you can read all of Jorge’s previous Bitesize Bug Reports\*\*™
\*\*by following the [Bitesize
tag.](http://www.omgubuntu.co.uk/tag/bitesize/)*

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
