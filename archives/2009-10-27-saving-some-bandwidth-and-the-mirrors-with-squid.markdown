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

So about half way through this cycle I moved to squid for my apt-caching
needs since all the others ones would fail or be rewrites of other ones
or something. Ends up squid is real easy to use and I get the bonus of
caching everything instead of just .debs. It’s been real solid for me.
Here’s how mine is set up if you’re looking to do a bunch of upgrades
and want to save time and load on your local mirror.

1.  Find a machine you want to be your server.
2.  Install squid: `sudo apt-get install squid`
3.  Configure squid by editing /etc/squid/squid.conf (Warning, this file
    is probably the most commented file in the history of UNIX so
    it’s big)

By default squid won’t accept connections from remote hosts so I
modified one line to be like this (My server is not internet-facing): \`
http\_access allow all \#forgive me kees \`

And … add this to the bottom (I nicked this from another blog and
cranked the numbers up but can’t find it now for some reason, shucks for
attribution): \` refresh\_pattern deb\$ 1577846 100% 1577846
refresh\_pattern udeb\$ 1577846 100% 1577846 refresh\_pattern
Packages.gz\$ 1440 100% 1440 cache\_dir ufs /var/spool/squid 15000 2 8
maximum\_object\_size 409600 KB \`

1.  Restart squid: `sudo /etc/init.d/squid restart`
2.  Configure your machines to use your server, either by setting it in
    the GNOME Proxy gui thing (squid defaults to port 3128 so make sure
    you specify that), or in http\_proxy in your environment, or for apt
    in /etc/apt/apt.conf:
    `Acquire::http::Proxy "http://192.168.1.117:3128"` Setting it in the
    GUI GNOME thing is easiest for me.

3.  Confirm it’s working. On the server do
    `sudo tail -F /var/log/squid/access.log` to watch the log. Now go to
    one machine and do an apt-get update and upgrade and the log should
    show a bunch of TCP\_MISS lines for each deb you download. Now go to
    the second machine and do the same thing. This time each deb should
    show something like TCP\_REFRESH\_HIT, which means squid is
    intercepting the request and sending the deb directly to
    that machine. Rinse and repeat. This will also work for PPAs
    and whatnot.

Random tips:

-   Use the same mirrors on every machine. If you have a mirror on one
    machine and the other machines don’t the debs won’t get cached.
    (Anyone know a fancy rewrite or something to get around this?)

-   Do one machine and then do the others when that one is done,
    otherwise if the one machine is partially done the other ones will
    catch up and you’ll end up with all the machines trying to pull the
    last few debs at the same time.

-   I haven’t figured out an easy way to have my laptop use a proxy when
    it’s connected to my home network, but have no proxy set when
    travelling, I have to do it by hand.

-   I set one machine to autodownload updates in the update-manager
    prefs, that way when I wake up in the morning the debs are already
    cached, making for quick upgrades as soon as you wake up. That’s
    what everyone does first thing in the morning right?

Any other bandwidth saving tips? Leave a comment!

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
