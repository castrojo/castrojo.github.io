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

After months of tweaking and gathering feedback, I am happy to announce
the beta of the [Ubuntu Upstream
Report](https://edge.launchpad.net/ubuntu/+upstreamreport). The upstream
report is a real-time page that lists the Top 100 projects in Ubuntu
sorted by open bugs, and also shows us how many of those bugs are
“upstreamable”, and how many of those have an actual link to an upstream
bug tracker.

The intent of this page is to be used as a tool by Ubuntu Developers to
track how well their linkages to upstream bug trackers are, and provide
a list of bugs that are possible “targets” for them to push upstream.

When you first see it it’s quite overwhelming, so let’s look at how we
got to this report.

### Understanding the Problem

When I talk to bugmasters for large projects usually a generic term I
hear is “So and so is doing a good job with package foo” or “I’ve not
gotten a single bug report for my package bar, I had to go hunt someone
down”. While generally these comments are useful, nothing beats having
numbers. It would be nice to be able to talk to a maintainer and say
“We’ve been able to forward to you 90% of the bugs that we’ve Triaged.”
or in the worst case, be able to pinpoint which packages have poor
linkages so that we can put QA resources on that package to get better
linkages.

It’s also a problem for developers. There’s no “30,000 foot view” of how
well your bugs are being linked upstream, and you don’t really have a
“hit list” of possible bugs to upstream, you really just handle your
specific pile and do the best you can.

We wanted to provide a tool that not only shows upstreams how well we’re
linking and forwarding bugs, but a day-to-day tool for maintainers to
see where there are targets of opportunity to forward to upstream. And
lastly, for triagers we wanted to provide real-time working “bug lists”
that you can work through if you want to help be the bridge that
connects the downstream Ubuntu Package to the upstream project.

### Reading the Report

Let’s pick an example, I will use rhythmbox since it’s a package we ship
by default and most people are familiar with it:

\[![Report\_headers\_2\](http://stompbox.typepad.com/photos/uncategorized/2008/09/24/report\_headers\_2.png)](http://stompbox.typepad.com/photos/uncategorized/2008/09/24/report_headers_2.png)
\[![Rhythmbox\_2\](http://stompbox.typepad.com/photos/uncategorized/2008/09/24/rhythmbox\_2.png)](http://stompbox.typepad.com/photos/uncategorized/2008/09/24/rhythmbox_2.png)

The first column tells you the source package name, pretty simple. The
next column is a check to see if there is a corresponding project in
Launchpad. By the time a project makes it to this list that should be
filled out. The little bzr icon is there if there is a code import of
the project in bzr. The next column is the bug tracker field. It is
absolutely critical that this field is filled and correct, you can’t
forward bugs to an upstream if you have no idea where they’re supposed
to go. :)

The next field, which you will notice is very red is the “upstream
contact” field. Ideally this is a person who is willing to be that
bridge between us and the upstream project. For a bunch of these there
are teams that handle this, in the case of Rhythmbox it is handled by
the desktop team. I’m going to leave these alone for now and address
them in a later blog post, I want to get to the meat. :)

#### The Triage Column

The first number in rhythmbox is 306. This means that right now there
are 306 open bugs against rhythmbox in the Ubuntu Bug Tracker. Of those,
191 are in the “Triaged State”, for a difference of 115, 62.42%. Note
how you can click on the number to get the list of bugs!

#### The Upstream Column

Ok, here’s the meat of the report. Of the 306 open bugs 227 have an open
upstream task. What is an upstream task? It looks like this:

[![Upstreamtask](http://stompbox.typepad.com/photos/uncategorized/2008/09/24/upstreamtask.png)](http://stompbox.typepad.com/photos/uncategorized/2008/09/24/upstreamtask.png)

Sometimes, we can’t find an upstream bug report for the bug, so people
open a blank upstream task, this is PERFECTLY OK! Sometimes all that is
needed is a developer to acknowledge that it is indeed an upstream bug;
for example Jonathan Thomas did this for [bug
132375](https://bugs.edge.launchpad.net/ubuntu/+source/kdebase/+bug/132375).
(I’ll come back to this bug in a bit)

So ideally when someone determines this someone involved in the bug
report should do the due diligance of filing the bug upstream. Sometimes
this doesn’t happen, people are busy with real life, or they might just
be triaging a few bugs and can make the determination that it’s upstream
but not have the time to go through the steps of filing it upstream.
That is perfectly OK because when someone marks something upstream and
leaves it blank, it shows up in the next column:

#### The Watch Column - aka. Low Hanging Fruit {#the-watch-column---aka-low-hanging-fruit}

Any bug that has an open upstream task … but is NOT linked to an
upstream bug tracker shows up in this column. These are bugs that we
have determined should be upstreamable but haven’t been linked yet. As
you can see, out of 227 upstreamable bugs Rhythmbox has 227 bug watches
to the GNOME Bugzilla. That is a pretty impressive number. Nautilus, 311
linked out 313 marked upstreamable. [Bug
132375](https://bugs.edge.launchpad.net/ubuntu/+source/kdebase/+bug/132375)
would show up on this list under kdebase.

### Workflow

So let’s look at an example on how to improve a project’s linkages.
kdebase has 76 out of 83 possible bugs linked upstream; 91.57% which is
quite excellent. The very last column, the delta, shows us those 9 bugs
that haven’t quite made it, so let’s take a look. Clicking on the 9
takes us to [bug
132375](https://bugs.edge.launchpad.net/ubuntu/+source/kdebase/+bugs?search=Search&field.status_upstream=pending_bugwatch%3Ethis%20list%3C/a%3E.%20These%20are%20bugs%20that%20someone%20has%20determined%20to%20be%20upstreamable,%20but%20HAVEN'T%20been%20linked%20yet.%20On%20that%20list%20is%20our%20%3Ca%20href=).

This my friends, is an awesome candidate to be upstreamed. The report is
an easy way to find upstreamable bugs! What should happen now is someone
files this bug in the upstream KDE bugzilla, and (don’t forget) to link
the launchpad bug to that new report. Instructions for linking are found
[here](https://wiki.ubuntu.com/Bugs/Watches). As soon as the launchpad
watch kicks off, this bug moves out of the delta column and into the
watched column.

You’ll notice that both kdebase and rhythmbox are marked “green”. Any
project with a 90% or above link rate shows up as green. This number is
pretty obvious and non-negotiable - if a bug is determined to be
upstream and is NOT forwarded upstream then it is in a FAIL state. ;)
The 10% breathing room is there for bugs that are determined to be
upstream but you’re waiting on more information or data or something
before you send it up.

### What happens next

Launchpad watches are awesome for one simple reason: When a bug is fixed
upstream we know about it. When we know about it we can target them with
resources. Launchpad watches feed the
[Harvest](http://daniel.holba.ch/harvest/handler.py?pkg=rhythmbox)
machine - which is useful because developers can find these low hanging
fruit and fix them.

### Why you should care

We have a ton of users, as a result of this, we get a ton of bugs. Many
of these users are new to linux, this leads to many bug reports that are
incomplete or just not good enough to send upstream. What we DON’T want
is people blindingly forwarding bad bugs upstream, we want our most
detailed, complete bugs sent up. This report gives us targets that we
should look at as candidates for sending bugs upstream. The kdebase
example I showed is “only” a wishlist bug, but still, upstream should
know about it. Bugs that show up in the “Triaged” state have been set
that way by the Ubuntu Bugcontrol team, those should be scrutinized as
candidates and sent upstream.

The real simple question to “why?” is because it’s the right thing to
do. We ship rhythmbox to millions of users, it’s our duty to ensure that
every one of those 227 bugs is sent upstream. If our users report bugs
and they don’t get to the authors, then chances are they won’t receive a
fix, and that isn’t very user-oriented. :D

### Tips on How to Proceed

-   Ubuntu Developers - If the Upstream column has a low percentage,
    then you’re probably not opening upstream tasks to your bugs.
    virt-manager has 0 out of 75 bugs marked as possibly upstream.
    Either we introduced 75 bugs to virt-manager or we’re not marking
    the upstreamable bugs with an upstream task.

-   Triagers - Use the last column to look for bugs where a developer
    has opened an upstream task - search the upstream bugzilla to see if
    it has been reported, if it has, link it! If it hasn’t been
    reported, you can follow [these
    instructions](https://wiki.ubuntu.com/Bugs/Upstream) to create a new
    bug in the upstream bugzilla to link it. If you get confused on how
    exactly to do this ask someone for help.

-   Upstream Developers - You can use the last column and use it as a
    list to check out bugs that we haven’t sent to you yet. If you have
    an Ubuntu user that pops into your IRC channel asking how they can
    help you can point them to this list.

-   Users - You can help “become that bridge” between Ubuntu and
    upstream by following these bugs and forwarding upstream
    as appropriate. If you find the same bug in the upstream bug tracker
    then make that link!

### Caveats

This report is still a beta but we consider it in good enough shape to
get it out there and get people working with it so we can fix it and
make it more useful for everyone. Currently there are the following
caveats:

-   Currently there are ubuntu-specific projects on there that don’t
    really have an upstream or where Ubuntu is the upstream, like
    software-properties, these will be removed.

-   Sorting is kind of wonky, you might need to refresh if you’re
    sorting columns a bunch of times (Graham is working on this as
    we speak!)

-   Right now we’re only showing the top100 projects according to open
    bugs - we should have a method of querying any package in
    the archive.

-   Some of the target bugs in the last column might be old or
    inappropriate - remember this column shows open upstream tasks with
    no links, clean these out and marking upstreamable bugs with an open
    task and this list will become useful to you!

-   The upstream report targets are not an excuse to NOT work with an
    existing team! Don’t just go in there and start forwarding bugs,
    work with the existing teams. Sometimes Ubuntu developers do NOT
    forward a bug until they have more information - if you just go and
    forward something when it is not ready you’re just creating more
    work for everyone, so if you want to work on something, let someone
    know! The desktop team doesn’t bite, I promise!

… and last but not least:

### The Upstream Report is Chuck Norris

a\) He has no emotion - he just reports numbers. Use it as a tool to
gauge where you are, and where you need to improve.

b\) Let me reiterate - having a “green” doesn’t get you off the hook! It
just shows how well your linkages are doing - low upstreamable bugs
stick out like a sore thumb - if a project you work on has 100 open
bugs, but only something like 3 are marked as upstreamable and you think
you’re doing awesome because you’ve linked those 3 and you get “100%” in
the linkages then you’re doing it wrong!

c\) If your numbers are bad, don’t panic! - the report was *designed* to
show you were things are bad, and give you a list of targets so you can
triage/forward appropriately. There will be instances where a bug might
show up that is inappropriate to send upstream. That’s fine, don’t
forward it. Use the list of targets as a short list of *possibles* to
look for candidates.

d\) If your numbers are awesome then congratulations, you’re doing the
right thing.

### The Bottom Line

At the bottom under totals we find that when we do find a bug we do a
good job (92%) of linking it upstream. The bad news is that only 17% of
our current bugs are marked as upstreamable. I look forward to seeing
how we grow this number and increase our linkages!

#### The Future

This is just a rough start - if you follow a bug workflow in your head
to it’s logical conclusion you can think up of many ways we can expand
this report - Do we have nice method for undoing a bad upstream link?
Apport crashes are pretty unique, is there a way we can automate that to
get that to upstreams in a nicer way? What can we do to improve
bugs.launchpad.net to make linking easier and less error prone? How can
Launchpad talk to upstream bug trackers to make this even more useful?

These are questions that we’ll be addressing as time goes on, in the
meantime I hope that this initial cut is useful for everyone. As always,
feel free to contact me, jorge at ubuntu.com with feedback - you can
report bugs here: <https://bugs.launchpad.net/malone>, please tag them
with “ubuntu-upstream-relations”. I’ve added this blog post example to
the [Ubuntu wiki](https://wiki.ubuntu.com/Bugs/Upstream/UpstreamReport)
- updates and changes will happen there.

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
