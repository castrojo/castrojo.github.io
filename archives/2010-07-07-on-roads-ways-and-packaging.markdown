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

Matt posted [his
thoughts](http://mdzlog.alcor.net/2010/07/06/weve-packaged-all-of-the-free-software-what-now) on
how the model of packaging software in OSS can change to adapt to new
user needs. LWN also [picked this up](http://lwn.net/Articles/395092/).
Some of the comments are heading down into details, so I thought I would
explain from a more general perspective on how I see the packaging
landscape instead of talking about tools. I don’t think it’s about
tools, it’s about the mindset.

To me there are two mindsets here. The first is the Windows way. The
idea that the OS comes bare, and you allow people to download and
install whatever they want from wherever they want. In the old days this
was floppies and CDs, and gradually evolved to the internet (downloading
.exe’s). Admins in controlled environments have .msi files, which they
can deploy via active directory.

And then there’s what in my circle of friends has always been known as
“The Debian Way”. This is a part of our culture that most new users have
the hardest time with. Why “hunt and peck” over the internet to find
what you need when the OS can provide that for you? Why update
individual apps when you can just update them all at once with one
system? And don’t forget the built in quality control, this way we lower
the risk of Bad Things(tm) being installed on people’s computers. Surely
people will totally get this!

So for years this was misunderstood, and people still wanted to go
download random files from the internet, and people who didn’t know how
it worked claimed that installing software in Linux is like the hardest
part ever, when really it was totally awesome. For those of us on The
Debian Way, things were pretty ideal. There were issues though:

-   Not everything was packaged. But then again this can be a
    “quality filter”. My friend Kyle Rankin has a saying “If it’s not in
    apt it doesn’t exist”. If something was more than a flash-in-the-pan
    it would get packaged.

-   If there is a long time between releases this means users get stuck
    with really old software, and miss out on the “buzz”.

-   If you were an upstream project and you did a stable release it
    might be a long time before that get to users. This can be
    infuriating if you’re fixing bugs but can’t them into user’s hands.

-   To this day people still want to go to websites and click on stuff
    and get software. And admit it, you’ve drank from the forbidden cup
    of random .deb on the web at one point or another!

The Ubuntu path, which inherits from The Debian Way(tm) kind of sort of
helped mitigate this, by doing time based releases, so upgrades can’t be
so old, and with PPAs users can wedge in a solution if they were
impatient.

Fast forward a few years and the iPhone’s app store is basically “apt”
with shiny and a quality assurance process on top. (The way Apple
handles the app process is a different topic). On this device you have
applications from one “repository”, there’s NO concept of installing
third party applications. Every one loves it. I talked about this when I
ran for GNOME board [a while
back](http://www.mail-archive.com/foundation-list@gnome.org/msg03690.html) and
I think it still applies.

And here’s the crux:

People who complain that applications are hard to install have no
problems using the “package systems” on mobile phones because they never
had to hunt and peck for apps on their brand new smart phones, even
though the locked down app stores on phones are just as “limited” as the
“limited” apps that are packaged in repositories. Why? Because modern
mobile phones never really let you install random applications from the
internet, so there was no expectation that this would work. Your PC,
however, did, and if you didn’t wrap your head around the model then you
just didn’t get it, and that’s how people end up on openoffice.org
downloading 146 meg tarballs which contain a bunch of .debs that you had
to manually install. And yeah, mobile stores let you update the
apps independently of the OS. On top of that, people thought that it was
totally ok to just throw random .debs, RPMs, whatever, and source
tarballs on the internet and that that was OK.

So as far as users were concerned … **FAIL**. No wonder people hate it!

As it ends up, it’s **all about presentation. **No one complains about
how hard it is to install random APKs from the web because that’s a
niche thing. App developers KNOW they need to get in the Android Market
and that that was the primary avenue to get applications to users. AT&T
is even
[blocking](http://www.mobilecrunch.com/2010/06/15/lesson-not-learned-att-locks-down-the-htc-arias-app-selection/)
third party apps, and no one will care. We collectively fail at linking
packagers with upstream developers, which is why when normal users go
searching for applications they end up with tarballs they can’t use.

Things like this is what we want to fix with the Software Center, we
want to narrow the gap between upstream software developers and users. A
buddy of mine who criticized the Debian way put it bluntly: “You guys
add artificial barriers between me and my users, and that sucks.” I
personally like to think as the Software Center as the refined “middle
ground” where we can totally continue to innovate as a Free Software
Whole:

-   No one in Ubuntu wants to keep users away from awesome apps, we want
    them just as badly as you do. We hurt when we see new apps and can’t
    get to them too.

-   We totally want to enable upstream app developers to get their stuff
    out there so people can use it.

-   We all want something easy, simple, but also secure. We don’t want
    hunt and peck randomness like one OS, but no one wants
    an arbitrary random rules (that change but no one tells you) of what
    goes in and what doesn’t like the other guys. We need to
    find Balance.

-   The old “distro model” needs to change, we need to be more agile to
    developer and user needs. This will take time.

So here we are. On one hand we have us old school people who like how
the system has worked. You tell new people to use the Center and we’re
good. I don’t have to worry that my wife will end up with a broken
computer because I trust the Ubuntu developers who upload to the
repository. At the same time more advanced users might want a little
bit-o-bling from the latest upstream applications, but at the same time
no one wants to upgrade to a -dev release of the distro to get new
software. Upstreams don’t want to deal with the mess so they just put
tarballs up on websites and move on.

It’s really nice how Google’s Chrome repository gives people what they
want when they want it. They provide stable releases all the way back to
Hardy, people don’t need to care about backports, updates, regression
testing etc. You get it right when they announce it. They have stable,
beta, and dev releases, and you can upgrade AND downgrade (something you
can’t do with Windows Chrome without reinstalling the whole thing!)
Google also have lots of resources. I am not sure that would scale for
everyone. Users adding 50 PPAs will also end in pain, so that doesn’t
scale either so I am not sure what the solution is but at the end of the
day the packaging spice must flow and it’s in our collective best
interest to solve it.

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
