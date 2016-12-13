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

At the end of every work day I check the wiki’s
[RecentChanges](http://wiki.ubuntu.com/RecentChanges) for cool new
stuff. I mean, who *doesn’t* do that. I ran into some of James Westby’s
work on daily builds, specifically this page on
[BzrBuilder](https://wiki.ubuntu.com/DailyBuilds/BzrBuilder) and I was
able to make a daily build of an upstream in about 5 minutes, that
includes reading the docs! Here’s what I did. First off, pick a project.
I picked [Quickly](http://launchpad.net/quickly), since it’s the new
black.

Then install the bzr plugin like in the instructions. Then I created a
recipe file like so: \` jorge@bojack:\~/dailies\$ cat quickly.recipe \#
bzr-builder format 0.2 deb-version 1.0+{revno}+{time} lp:quickly \`

Then it’s ONE command:

` bzr dailydeb quickly.recipe --key-id FFC27DD0 --dput ppa:jorge/ppa`

Booyah, that’s it. Now, we got lucky here since Quickly is all in
launchpad already and has a debian directory already in there. For other
projects I suspect that grabbing them from vcs-imports and then merging
in the packaging branch will also work, however I have not done this
yet, but if you want to try it, the
[instructions](https://wiki.ubuntu.com/DailyBuilds/BzrBuilder) are
available. So if your project is already in launchpad you can start
making dailies *right now*. Make sure you read up on [more
docs](https://wiki.ubuntu.com/DailyBuilds).

More than one way…
------------------

James isn’t the only person looking into dailies. The now-famous Fabien
Tassin has been working on this as well, but taking a different
approach. His scripts are available here:

<https://code.edge.launchpad.net/~fta/+junk/ppa-scripts>
<https://code.edge.launchpad.net/~fta/+junk/ppa-confs>

Fabien’s daily builds have been insanely popular, the chromium PPA alone
has over 10k users (and that’s just the fractional popcon numbers).
Also, odd that people keep the wine build around, but whatever.

![chromium-popcon-6](http://castrojo.files.wordpress.com/2009/08/chromium-popcon-6.png)

He also has them for the various mozilla projects, gwibber, and has just
set up one for network-manager. [Other
people](https://edge.launchpad.net/~gmpc-trunk/+archive/ppa) are using
it as well. Since they were
[announced](http://www.asoftsite.org/s9y/archives/158-Ubuntu-Mozilla-Daily-Archive-with-firefox-3.1-and-3.2-for-hardy,-intrepid-and-jaunty.html)
in February the Mozilla daily builds have about 10,000 users of Firefox
and over 1000 of Thunderbird. (Sorry no graphs for that, but look at
[numbers](http://paste.ubuntu.com/257135/).

Great Power, Great Responsibility
---------------------------------

Alexander
[mentions](http://www.asoftsite.org/s9y/archives/164-ubuntu-network-manager-team-offers-daily-builds-for-trunk-aka-0.8-now.html)
in his blog post on the ideal type of person to use daily builds.

> -   All advanced users that run the current ubuntu development
>     release (e.g. karmic for now) that also want to focus their
>     testing efforts on network-manager

> -   Users that have filed a bug against NM which then got fixed
>     upstream can verify the fix by trying our daily build.

> -   Since we are targeting 0.8 for karmic the dailies reflect what
>     will go into karmic soon. So if you like to run the bleeding edge
>     and like to report issues right when they happen, this PPA is
>     meant for you too.

> -   We also have jaunty builds, but those are not yet fully tested. If
>     you want and run jaunty please try them and report your findings
>     back (of course, be sure that you know how to recover from not
>     having network-manager network)

And James points out: “Obviously, as there is automation involved in the
process the resulting packages can be risky as they haven’t had human
verification. This means that there has to be some care taken with them,
and the project and packager should do there best to ensure that the
risks are minimized. They are also not something that an average user
should be using. With due diligence the benefits can certainly outweigh
the risks though.”

My view is that people will always want crack, and the availability of
things like PPAs certainly lowers the barrier for users to use your
software. But those people aren’t necessarily capable of giving you the
kind of bug reports you need to fix problems, or things might be in a
state where you know things are broken and don’t need bug reports
spamming you every day. Chromium even tells you “Don’t file bugs without
doing the work!”

I am interested in how upstreams perceive the idea of daily builds, I’m
sure there are plenty of plusses and minuses to having them. However, I
am convinced that Chromium’s spike in popularity in Ubuntu is because of
the ease in which it is to use them. So the real question becomes, do
the benefits of getting more testers outweigh [people arguing in
circles](http://code.google.com/p/chromium/issues/detail?id=9007)?

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
