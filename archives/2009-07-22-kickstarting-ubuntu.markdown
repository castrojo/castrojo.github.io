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

My friend Andrew came over yesterday and helped me set up
dhcp/dns/kickstart on a spare machine because it would help me out for
testing karmic and after 2 years I basically have no idea how to
sysadmin anything.
[Here](https://help.ubuntu.com/community/PXEInstallServer) are the basic
instructions.

I have a squid proxy at home that I use to cache my .deb files (See this
[great
post](http://shadow-file.blogspot.com/2008/12/ditching-apt-cacher-ng-for-squid.html)
for more information) so that I am not constantly hammering my local
mirror with my 6+ machines in the household. Last cycle I was getting
frustrated at how long it took me to do testing, so I vowed to make it
all efficient so I can do real hardware and VM installs easily. Plus you
know sometimes we have dinner parties and whatnot and it’s polite to
offer Ubuntu to your guests. So after we set up kickstart I wanted the
installer to use my squid proxy so that I could take advantage of all
the caching goodness. That’s when I discovered that one can use preseed
arguments in your kickstart file and it Just Works(tm):

> preseed mirror/http/proxy string http://chichi:3128/ preseed
> popularity-contest popularity-contest/participate boolean true preseed
> finish-install/reboot\_in\_progress note \#NTP preseed clock-setup/ntp
> boolean true preseed clock-setup/ntp-server string ntp.ubuntu.com
> \#One big partition preseed partman-auto/choose\_recipe select atomic
> \#Add local repo

Tasks
=====

preseed tasksel tasksel/ubuntu-desktop

Packages
========

%packages banshee gnome-do openoffice.org ubuntu-restricted-extras …
etc…

I didn’t know you could do this!! Now I can get my preseed goodness and
not have to relearn a whole new system. (Right now some of you are going
omg use d-i, FAI, or one of the other million ways to do this). I prefer
ks for two reasons, a) everyone I know uses it in production, and b) I
can rip off other people’s ks scripts since they seem to be more common.
This (and other) features have probably been around for a while, I need
to spend more time hanging out with installer people.

Help needed: For some reason the karmic installer installs
ubuntu-desktop, and the package gets installed, but none of the
dependencies do. So after the install I get a semi-complete ubuntu
desktop. After removing ubuntu-desktop and then reinstalling it /then/
it goes and grabs firefox, tomboy, and the rest of the desktop. I’ve
tried the preseed line you see above and mentioning ubuntu-desktop
explicitly in the %packages section to no avail. It doesn’t feel like a
bug as much as I think I missed a step myself. On a positive note,
installing ubuntu-restricted-extras is automated, I don’t get bothered
for licenses or any of that, so woo hoo on that front.

Other random thing: Why not run a local ubuntu mirror? I set up an rsync
and everything and started with main, then I realized that throughout
the course of a cycle I am constantly updating and installing stuff, so
it’s already in my squid cache, why have rsync firing off hitting my
mirror when I keep most of the .debs locally anyway? Sure if I was at a
University or something a full mirror would make more sense.

Related story on LWN about [package repository
proxies](http://lwn.net/Articles/318658/). I still find the squid method
to be the most reliable for me, though hopefully apt-zeroconf will make
this transparent and easy for normal people. (The caching part, not the
kickstarting part.)

What ways are you sysadmins out there deploying Ubuntu? Share your tips
and tricks in the comments.

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
