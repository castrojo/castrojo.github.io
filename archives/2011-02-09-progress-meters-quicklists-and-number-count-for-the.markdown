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

Here’s something I’ve been waiting for that I’m sure application authors
will enjoy: 

![](http://media.tumblr.com/tumblr_lgd5hzIjsv1qb5bmy.png)

We now have an [API for
applications](https://wiki.ubuntu.com/Unity/LauncherAPI) to leave a
progress meter and/or a number on their launcher. The wiki page is a bit
sparse so expect more detail there over the coming week.

What we need to do
------------------

Well, the first thing I’m working on is getting the [wiki page up to
shape](https://wiki.ubuntu.com/Unity/LauncherAPI). We’re going to need
examples for different languages, and basically make the page useful for
application developers. I’m on that this week. I could use a hand here
if someone wants to dig in.

Next, we need people to think about where this is useful. So right away,
you’re thinking mail apps, Transmission and Deluge, USC, update-manager,
etc. 

The library is called [libunity](https://launchpad.net/libunity), which
is the same library you’ll use for
[Places](https://wiki.ubuntu.com/Unity/Places) and stuff, and you can
use it in one of two ways:

-    Directly in your application, just link up to libunity, you’ll
    notice the the API is similar to app indicators. This is on purpose,
    so if you’ve already got libindicator support in your app, this
    should just be additive and straightforward.

For example, right now your application might put a “new message”
counter in the messaging menu, this is designed so that you can also
just plop the same number right on the launcher icon too.

-   Or standalone, like the example on the wiki page - this is for you
    people who want to write little wrapper scripts to monitor something
    (like say, your mutt instance on a remote server, *hint hint*)
    (think of the things we could get from byobu running on
    your server!)

Application developers, we’re looking for feedback
for [libunity](https://launchpad.net/libunity), feel free to file bugs.

### How You Can Help

Feel free to start filing bugs in Launchpad for applications to support
this. Make sure you tag em “bitesize”, as these will be easy for people
to dig into and make work.

Got a favorite application? Link the up to our resources or they can
[contact us directly](http://unity.ubuntu.com/contact-us/) if they want
help with linking these up.

### Other Unity Improvements that Just Landed

Part 2 of the things that landed today are much more user visible,
mainly, drag and drop for the Launcher:

-   Drag stuff into the trash

-   Being able to drag files onto apps, for example select 4 text files
    and drag all of them onto the text editor and it will open them all
    up at once.

-   Drag any .desktop files right into the launcher, but you can’t drag
    from the Dash yet, but you will be able to soon. For an example of
    this drag and drop applications from /usr/share/applications to get
    an idea.

-   Drag anything from a GNOME menu, GNOME Panel, and any dock that does
    xdnd into the launcher (for those of you with frankendesktops) -
    remember that we already import those launchers on first run.

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
