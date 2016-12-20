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

Here’s a cool gift to the community from charm hero [John
Patterson](https://launchpad.net/~nextrevision).

We now have a full [OpenVPN Access
Server](http://jujucharms.com/charms/precise/openvpn-as) ready to deploy
in the [Juju Charm Store](http://jujucharms.com).

Deployment is easy:

    juju deploy openvpn-as
    juju set openvpn-as password=mycoolnewvpn
    juju expose openvpn-as

The just a quick `juju status` to get the public address and hit it with
http://ipaddress/admin to configure the VPN server. Then you’re done,
you have an OpenVPN server.

Of course to use a VPN you need to configure your clients, thankfully
John has [included
instructions](http://jujucharms.com/charms/precise/openvpn-as) for Mac,
Linux, and Windows. Using OpenVPN commercially? No worries, there’s even
an option to pass along your OpenVPN license to the deployment after the
fact. There’s also some other goodies in there you’ll want to check out.

One current limitation is that you do need a bootstrapped environment to
deploy this, so for individuals it might be cost restrictive to run 2
instances, but if you’re a larger organization with multiple users this
won’t be an issue. Still, work continues to allow for multiple services
to run on the same machine, and we should have a nice, single-machine
OpenVPN solution for you by the end of the summer.

In the meantime, enjoy OpenVPN, nice work John!

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
