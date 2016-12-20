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

TLDR: 12.04.2 ISOs are NOT just rolled up updates, they’re 12.04 with
newer kernels.

I’d like to point out some changes to things that might affect our
server users. The last 12.04.2 point release is the first real release
where the [LTS Enablement
Stack](https://wiki.ubuntu.com/Kernel/LTSEnablementStack) is in effect.

There are some things I’d like to highlight for those of you not reading
the release notes, as this is different from how we rolled point
releases in the past.

-   New installs from the 12.04.2 ISOs will get a *newer kernel* (3.5)
    than 12.04 (3.2).
-   Machines currently running 12.04 will NOT receive these kernel
    upgrades, only new installs from the *new ISOs* will get the
    enablement stacks.

Recommendations:

-   The 12.04 and 12.04.1 ISO’s are at
    <http://old-releases.ubuntu.com/> - you’ll likely want to keep a set
    for yourself if you want to roll out with the same exact kernel for
    your deployments - you’ll probably want to have all three ISO sets
    on hand depending on your hardware.
-   The original 12.04 stack will continue to be maintained for 5 years,
    if you don’t need the new kernel, you don’t need to use it.
-   In the past if new hardware rolled out and didn’t work with the LTS
    you were kind of stuck with either backporting a kernel, or (what I
    reluctantly did) deploy a non-LTS release until the next LTS came
    out, at which point you would rebase on the new LTS.)

What this means is that the life of the LTS is now much longer, while
also giving you the option of sticking with a stable userspace with
newer hardware support (if you need it). The [wiki
page](https://wiki.ubuntu.com/Kernel/LTSEnablementStack) has a bunch
more details, please check it out.

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
