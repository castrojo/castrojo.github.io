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

While we were at Debconf Jono and I tweaked the
[5-a-day](https://wiki.ubuntu.com/5-A-Day) page to be simpler and less
confusing. One list of possible targets we added is the list of
[unlinked upstream
bugs](http://people.ubuntu.com/~brian/reports/database/unlinked-bugwatch.html).
These are lists of bugs where people have pasted in bug reports in
comments but have NOT linked to it via Launchpad’s “Also affects
project…” feature.

Why linking bugs upstream is important
--------------------------------------

Just mentioning a bug report that is upstream is only one aspect - sure
it’s useful, but linking it allows us to *query* Launchpad for these
bugs, and more importantly *track these bugs programmatically* so they
get on the right person’s radar to fix it. Instructions for doing this
are [here](https://wiki.ubuntu.com/Bugs/Watches). Now, let me show you
an example on why this is important.

Example bug
-----------

Bernhard Schmidt reported [this
bug](https://bugs.launchpad.net/ubuntu/+source/rdesktop/+bug/84072) on
rdesktop on February 8th. Basically, he wanted rdesktop to be compiled
with IPV6 support. Bernhard also opened up a bug [in
Debian](http://bugs.debian.org/cgi-bin/bugreport.cgi?bug=432299). Three
days ago Laszlo Boszormenyi reported that it was fixed in Debian with
the upload of rdesktop 1.6.0-2.

Ok so now what? The bug just sits there right? Well, that depends. As it
happens, I was doing my 5-a-day and stumbled across this bug - and I
thought “This bug is fixed in Debian already, it should be on someone’s
hit list to fix, right?” Wrong. Or am I? No way to tell for sure, and
short of Bernhard chasing someone down or having someone else who can
actually fix it find it isn’t very efficient. If only there was a list
of easy, low hanging fruit … like say
[Harvest](http://daniel.holba.ch/harvest/)!

I linked the bug to Debian bug in Launchpad. The next time the bug watch
is updated Harvest will find it, and it will show up in Harvest
automatically. Now as people trudge through Harvest the bug is listed as
a possible fix and they can fix it.

Oiling the machine
------------------

So, what needs to happen for this to be as efficient as possible?

-   Bug reporters - Do continue to report bugs upstream like Bernhard
    did in this case. Well done Bernhard! Instructions for filing bugs
    in upstream trackers are
    [here](https://wiki.ubuntu.com/Bugs/Upstream).

-   Bug reporters and triagers - Don’t just throw a URL in the comment
    box, link it via Launchpad
    ([instructions](https://wiki.ubuntu.com/Bugs/Watches)).

-   Bugsquad / Experienced Bug Triagers - encourage people to link bugs
    during Hug Days.

-   Ubuntu Developers - Keep monitoring Harvest for easy
    “sync-from-Debian-or-upstream” bugs.

Lessons Learned
---------------

As you can see, linking bugs upstream helps get bugs moving in the
process, and eventually end up in things like Harvest or the “bugs fixed
elsewhere” pages. People write tools and scripts to find these bugs,
especially if they’re resolved upstream, which makes it easier for
people to find so that the fixes can be shipped to users, which is what
this is all about!

Now let me put my Jordan Mantha hat on: “But Jorge, getting it on
Harvest is one thing, that’s only half the solution. Getting someone to
find it and fix it on the other hand …” Yes, absolutely. If you think as
this entire Harvest workflow as one big machine, then upstream linkages
are feeding the machine, but at the end of the day it needs to spit out
bushels out the back.

So we need developers to fix these bugs - which is why we have things
like Ubuntu Developer Week, MOTU mentorship, sponsorship, Harvest, etc
to grow the developer community. This is a tough area to grow, but we
are making progress, and tools like Harvest are making things easier I
think, in the meantime, keeping the machine well fed is still better
than a bug sitting in Launchpad all by itself …

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
