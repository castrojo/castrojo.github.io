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

mpt pinged me today to ask why Empathy has two icons in the panel.

[![](http://castrojo.files.wordpress.com/2010/03/sn7ak.png)](http://castrojo.files.wordpress.com/2010/03/sn7ak.png)

That’s odd, what is that yellow icon on the left?!? I responded that we
didn’t we ship it that way, we ship it with messaging indicator support
built in! You have to go check a box to turn that off. Likely he flipped
the box at some point in his install and forgot about it. This happens
to everyone all the time!

I don’t maintain Empathy, the desktop team does, so how did I know we
shipped it that way out of the box? I checked on a new system, with a
fresh ISO from the day before, *right then and there* when he asked the
question. How do we keep track of what we’re shipping by default and
what we’ve customized on our own day-to-day PCs?

Enter [testdrive](https://edge.launchpad.net/testdrive). It’s in Lucid
already or if you’re in Karmic use the PPA.

After that I dragged the little wheel into my panel. When you click on
it you get something like this:
[![](http://castrojo.files.wordpress.com/2010/03/screenshot-terminal.png)](http://castrojo.files.wordpress.com/2010/03/screenshot-terminal.png)

Now you need to wait for a minute. The first time you do this it will
download the whole ISO. So just stick an old one in the cache directory
or let it sync. Don’t worry, after the first time it gets much easier.
Then a few minutes later we can confirm our findings:

[![](http://castrojo.files.wordpress.com/2010/03/screenshot-1.png)](http://castrojo.files.wordpress.com/2010/03/screenshot-1.png)

Aha, indeed by default we don’t ship that weird icon in the tray. Whew!
The best part of this is tomorrow when we need to know about how
something is working in the default install we just click on the wheel,
let it sync, test, confirm, and then move on! And since it keeps a cache
you never have to redownload the whole ISO. And there’s things in there
for -server, netbooks, and other arches, so it’s handy to check things
across different kinds of Ubuntu.

This is great for confirming bugs and checking out what’s new!

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
