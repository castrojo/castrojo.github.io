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

I checked out [Joseph
Schmidt’s](http://californiaquantum.wordpress.com/) blog post on
reporting bugs upstream and I thought I would respond to clear some
things up and explain how we do things around here in Ubuntu land.

Josephs starts off with “I am not trying in any way to pick on Ubuntu.
They are just keeping statistics in a way I can put some numbers behind
my rant.” Heh, ok, fair enough. However, we do have an [Upstream
Report](https://launchpad.net/ubuntu/+upstreamreport) where we do break
this down by package. This is way more useful to study than the page of
[\~800](https://bugs.edge.launchpad.net/ubuntu/+bugs?field.status_upstream=pending_bugwatch&field.status_upstream-empty-marker=1&start=0)
or so pile of bugs.

It would be easy to point at a big pile of bugs and come to conclusions.
But let’s look at some of these bugs. Some of these are old, they might
be fixed in ubuntu but not in another component; I see a bunch that can
be resolved (they’re stale and rotting), I see a bunch that just aren’t
very good bugs to begin with. Still, it’s a pile of bugs that need to be
fixed or resolved.

However, it’s not just about numbers, it’s about quality and context. If
today we told all the bugsquad members to automatically forward every
Banshee bug we get to upstream we would overwhelm them with badly
reported bugs and actually hurt the project. What we strive to do is to
act as a good filter for upstreams so that when they get a forwarded bug
report from one of our triagers they get the information they need to
fix the bug. Doing this with consistency across an entire project is
*hard* which is why we are always doing training classes during openweek
and hug days, targetting upstreaming bugs during hug days, and we even
have [a
page](http://qa.ubuntu.com/reports/launchpad-database/unlinked-bugwatch.html)
that I trudge through nearly every day where people are leaving links in
comments but not linking. I usually send them a mail explaining how to
link bugs.

This last week we had a [Hug
Day](https://wiki.ubuntu.com/UbuntuBugDay/20090618) with the Empathy
folk. Look at that list of bugs, those aren’t a pile, those are a
specific targeted set of bugs in context with the hug day - we want to
be efficient and get the most bang for the buck, that means looking at
“the pile” and prioritizing and figuring out which ones upstream wants
to see the most. How do we know which ones upstream wants? Having a QA
relationship with the upstream is a great start. In this case we have a
wonderful upstream who works with our desktop team to make this work.
This is a great example of teamwork, we have many others. We also have
some poor ones I am sure. (And if you are an upstream who feels we suck
at this, let me know immediately)

What else are we doing? As it turns out, many incoming bugs tend to be
of poor quality. It’s not the person’s fault, a good bug report is an
acquired skill that needs practice! We have a great tool called Apport
that fires off when an app crashes. It has the capabilities to gather
information from the user and stick it in a bug report. It’s handy. We
want more people to use it because it cuts down on the mundane bug
ping-pong discussion. “What version, what distro?” etc. We are making an
even more concerted effort to [increase apport
usage](https://wiki.ubuntu.com/QATeam/Specs/IncreaseApportAdoption)
among our users so that the bugs coming in start off being better. When
I ask upstreams what they think of apport crashers bugs forwarded to
them the result is usually very positive.

Please remember that we are very, very sensitive to turning on something
that will autospam an upstream bugtracker, and in my opinion, rightfully
so. Forwarding bugs to upstream isn’t fixed with a shotgun, it’s fixed
with a scalpel. It takes time to go through those and make sure the
right ones get forwarded. We have two guys in Ubuntu that are really
good at this, they’re the [top 2
reporters](http://bugzilla.gnome.org/utils/stats-2008/top-reporters.txt)
of bugs for GNOME last year. This is the kind of activity we want to see
across the board and doing this properly is very important to Ubuntu and
Canonical - if you’re an upstream and you feel like we can improve in
this area, please get a hold of me.

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
