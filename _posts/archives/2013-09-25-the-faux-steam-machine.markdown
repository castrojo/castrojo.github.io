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

Now that everyone is talking about
[SteamOS](http://store.steampowered.com/livingroom/SteamOS/) and [Steam
Machines](http://store.steampowered.com/livingroom/SteamMachines/) I
thought I’d blog about my “Faux Steam Machine”. SteamOS is basically a
Linux-based OS, and we know that the SteamBox is basically a PC. And
while people are guessing that the announcement on Friday will be a
controller, I went ahead and assembled my own with my own stuff.

Certainly not “Steam Certified”, but it’ll tide me over until I can buy
the real hardware, and it’ll let me follow along with development of
Steam at the “Big Picture” level. This is all pretty straightforward and
there’s nothing new in this post that you haven’t been able to do
before. It’s just now that Valve is committed to this direction I want
to follow along – especially as the number of titles coming out
continues to increase.

![](http://www.jorgecastro.org/images/steam.jpg)

For this tutorial you need:

-   An Ubuntu machine with good video performance. I have an Nvidia
    based machine. You need to install Steam on this machine.
-   [This wireless
    receiver](http://www.amazon.com/HDE-Wireless-Receiver-compatible-Xbox-controller/dp/B0096PLB9O)
    which enables you to reuse your Xbox 360 controller on your PC.
-   An Xbox 360 controller or some other wireless gamepad.

First you need to get the controller working in Ubuntu:

-   [How do I get a wireless XBOX 360 controller
    working?](http://askubuntu.com/q/165210/235)

And now, make a Steam session:

-   [Can I run Steam as its own standalone
    session?](http://askubuntu.com/q/302488/235) - this is great because
    it allows us to just login to the machine and then Steam fires up
    automatically in big picture mode. Kudos to you thor27 (the author
    of this little integration bit).

And finally, turn on auto login in LightDM so that our machine just
boots right into Steam with no user input:

-   [How do I enable autologin in
    LightDM?](http://askubuntu.com/q/51086/235)

Steam updates itself at the client level so there’s no need to worry
about that, the final step for a console-like experience is to [enable
automatic updates](http://askubuntu.com/q/9/235) and you should be good
to go!

TODO
----

-   There’s certainly some work we can do in Ubuntu to make configuring
    gamepads suck less.
-   There’s a [Steam
    repository](http://repo.steampowered.com/hometest/pool/steam/p/plymouth-theme-steam/)
    that has some goodies like a Steam Plymouth theme, this would make
    first boot look real slick.
-   Does anyone know if there’s a similar cable for PS3 controllers?
-   Performance: I assumed that loading Steam in a dedicated session
    would lead to better performance but it’s actually slower than
    running it in Unity. I think it has something to do with Steam
    running in the stripped down XFCE window manager that doesn’t have
    compositing? Need to investigate.
-   Someone on reddit mentioned that SteamGuard/login in could be a
    problem but I haven’t run into those issues yet.

</div>

<div class="share">

<div class="addthis_toolbox addthis_default_style">

[](){.addthis_button_tweet} [](){.addthis_button_google_plusone}
[](){.addthis_counter .addthis_pill_style}

</div>

</div>

<div id="comment" class="section">

<div id="disqus_thread" aria-live="polite">

Please enable JavaScript to view the [comments powered by
Disqus.](http://disqus.com/?ref_noscript)

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
