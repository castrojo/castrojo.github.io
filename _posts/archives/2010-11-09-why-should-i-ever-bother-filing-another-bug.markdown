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

Here’s a person upset about how [bugs are
handled](http://lists.fedoraproject.org/pipermail/devel/2010-November/145193.html)
in Fedora.

Here’s a person upset about how [bugs are
handled](http://www.linuxjournal.com/content/ubuntu-bug-reporting) in
Ubuntu.

Things I’ve learned here:

-   People have no idea (or care) where the problem comes from, they
    don’t care if it’s “upstream” or “distro”, they just want their
    software to work, and they don’t care who fixes it.

-   We’re not the only project to face this challenge.

-   [This
    person](http://www.linuxjournal.com/content/ubuntu-bug-reporting#comment-358449) thinks
    that we can bring pessulus/sabayon fixes to 7.04; a distro that is
    out of support, and even thought Scott Balneaves is now a
    contributing upstream; it doesn’t help this person who is stuck in
    some old version of Ubuntu, how do we help him?

-   mpt and evan’s talks [concentrate on fixing the feedback loop
    between distro and app
    developers](http://ubuntudevelopers.blip.tv/file/4324483/).  When it
    comes to application developers, make no mistake, this is the **real
    fix**. This doesn’t fix it for “plumbing” though (see below)

So how do we fix this for plumbing? Those of us who have been around
kind of know how this works. “I have a broadcom card, and it worked with
foo distro, and then I upgraded, and it broke, so I moved to bar distro,
and it worked; amazing, therefore bar distro is the win and foo is
crap.”

My experience in this area was at Ohio Linux Fest. I hadn’t gone to a
LUG meeting in a long time and I got into the elevator and ran into a
guy from the LUG, after initial hellos he was like “Wow, what the /fuck/
happened with Lucid, worst release ever, I can’t even connect!”

I was in a serious state of anxiety. Here I was, pouring my heart into
this damn thing. And not just coworkers at Canonical, but our immense
community contributors, pouring our heart and souls into this release,
and to be slapped in the face with failure, ouch! What was he upset
about? Some stupid *work around he applied 2 years ago* to get his
stupid Broadcom wireless card working. And on an upgrade it broke.

**As it ends up we’ve reached a new level of what people expect**.

My “linux geek correct” answer would have been “Hey bro, you have a
broadcom card, it’s a saving throw; each distro release has different
set of variables”. If you’re lucky you roll a natural 20 on a certain
release of a distro – and if you’re lucky an upgrade is totally easy. I
don’t even know what to say to the people to who own [these realtek
cards](http://askubuntu.com/questions/tagged/realtek). People are still
recommending “ndiswrapper” for these cards. That’s basically “Hey, I
can’t fix your problem, so here’s a work around”. That’s not
sustainable.

And as we know the people with broadcom cards don’t even get to roll the
dice, they’re still waiting! It would be nice to reset the board and say
“You’ve been hosed for years, but this time we’ll get it right.”

What a mess!

**So in conclusion**

I don’t think there’s something we can fix here. If someone rolls the
ndis20 and gets a working wireless, then … yay? We can perhaps do a
better job of explaining to users that they got lucky.

I don’t know much about about how Fedora does bug reports (or Ubuntu for
that matter), but I am pretty sure if you have a Broadcom card that it
will be a horrible piece of pain for you regardless of what distro you
use. (Until the newer drivers are integrated, and even then there’s no
guarantee that those will work with both your older distro AND your
older hardware.)

**Hey, I’ve heard this before.**

Of course you have, [Dan Williams has been
preaching](http://blogs.gnome.org/dcbw/) this for years. And, as it ends
up, every distro has bugs. Every day I hear people “I am switching from
foo to bar, they fix bugs!” … but in reality, we’re all in the same
level of doom, as it stands today if you have a broadcom wireless card,
you will be doomed; roll the dice. Depending on your video needs, ATI or
NVIDIA? Roll the dice. Doomed.

If your hardware works with no workarounds, send the manufacturer a
note. If it doesn’t work, then don’t buy it! If you want to make a
difference, vote with your dollar!

**Some conclusions…**

-   UNIX is our generation’s fault; let’s not leave this burden with our
    children, let’s at least leave them a list of things they can fix.

-   Let’s spend more time rewarding hardware manufacturers who do the
    right thing than dogpiling manufactures that might not know how to
    support Linux.

-   Instead of flaming people who are frustrated that their computer
    doesn’t work maybe we should suck it up and deal with their bad
    attitude as long as it fixes the problem – it’s been proven over and
    over that people will do the right thing if they’re treated right.

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
