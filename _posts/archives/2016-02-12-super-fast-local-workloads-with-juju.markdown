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

I was at [Config Management Camp](http://cfgmgmtcamp.eu/) last week in
Belgium and I ran into James Page, who was running OpenStack on his
laptop. I mean a real OpenStack in containers, not a devstack, a real
thing you could poke at. He would stand it up, do a bit of work on it,
commit, test, tear it all down, retest, and so on.

He had repartitioned his hard drive so he could have a ZFS partition,
and together with LXD and the [OpenStack Juju
Charms](https://jujucharms.com/openstack) it all just worked and was
very fast. His Thinkpad X230 was sweating a bit, but it all worked.

I had to have this. Real instances with ip’s that behave just as they
would on a real cloud, except you don’t spend money, and thanks to LXD
and ZFS, hella fast. It’s up to you if you want to run xenial a few
months before release, but for me it’s worth it, so I went all in. Here
are my notes:

First off you need a machine. :) I needed to redo my workstation anyway
so this became an evening of moving drives around and scrounging some
parts. When I was done I had an i7 3770, 16GB of RAM, 4x2TB drives, and
2 SSDs.

Step 1 - Installation
---------------------

Install Xenial. I installed this on one of my SSDs. I used the normal
`ext4` filesystem. Next I had the 4x2TB drives and a 60GB Intel SSD,
let’s put the spinning rust in a mirror, and use the SSD as cache for
some decent writes (EDIT: Apparently the cache command in this context
is for reads, not writes, thanks Manual Zachs for the correction). Feel
free to set it up how you wanted, but I wanted a bunch of room so I
could run large workloads and not worry about space or speed.

    # apt install zfsutils-linux
    # zpool create home mirror /dev/sda /dev/sdb /dev/sdc /dev/sdd cache /dev/sde

As you can tell, `/dev/sde` is the SSD and we’re just going to use the
array as our home directory. If you’re in your desktop you’ll want to
logout and not be in your home directory so you don’t step on yourself
when you do this. After some activity, you can see the SSD start to be
used as a cache device:

    # zpool iostat -v

                   capacity     operations    bandwidth
    pool        alloc   free   read  write   read  write
    ----------  -----  -----  -----  -----  -----  -----
    home         132G  7.12T      3     64   314K  5.34M
      sda       33.0G  1.78T      0     16  78.8K  1.33M
      sdb       32.9G  1.78T      0     16  78.0K  1.33M
      sdc       32.9G  1.78T      0     16  78.7K  1.34M
      sdd       32.9G  1.78T      0     16  78.8K  1.34M
    cache           -      -      -      -      -      -
      sde       25.9G  30.0G      0     34  41.0K  4.19M
    ----------  -----  -----  -----  -----  -----  -----

Step 2 - LXD configuration
--------------------------

Now time for our containers …. first install what we need:

    sudo apt install lxd
    newgrp lxd

The newgrp command puts you in the lxd group, and you don’t even need to
log out, bad ass. Now we tell LXD to use our ZFS pool for the
containers:

    lxd init

And follow the directions, select zfs and put in your zpool name, mine
was called `home` from the command above.

LXD needs images of operating systems to launch containers (duh), so
we’ll need to download them. While my host is xenial, we want trusty
here because just like the real world, cloud workloads run on Ubuntu
LTS:

    lxd-images import ubuntu trusty amd64 --sync --alias ubuntu-trusty

Now chill for a minute while it gets images. Ok so now you’ve got lxd
installed, let’s make sure it works by “sshing” into the container:

    lxc launch ubuntu-trusty my-test-container
    lxc exec my-test-container /bin/bash

And there you go, you’re own new OS container. Make as many as you want,
go nuts. Make sure you check out the fine docs at
[linuxcontainers.org](https://linuxcontainers.org/)

Exit out of that and move on to step 3!

Step 3 - Modelling Workloads on your shiny new setup
----------------------------------------------------

Ok now we need to put something awesome on this. Check out the [docs for
the LXD provider](https://jujucharms.com/docs/master/config-LXD) for
Juju, here’s the TLDR:

    sudo apt-add-repository -y ppa:juju/devel
    sudo apt update
    sudo apt install juju-local

OK, now let’s tell Juju to use LXD:

    juju init
    juju switch lxd
    juju bootstrap --upload-tools

Now let’s plop a workload on there … how about some [realtime syslog
analytics](https://insights.ubuntu.com/2015/09/24/realtime-syslog-analytics/)?

    juju deploy realtime-syslog-analytics

Nine containers worth of Hadoop, Spark, Yarn, Flume, and we’ll plop an
[Apache Zeppelin](http://zeppelin-project.org/) on top to make it all
pretty:

![](http://www.jorgecastro.org/images/spark.png)

Since we’re fetching all those Hadoop resources it’ll take a bit, on my
system with decent internet about 10 minutes total from zero to
finished. Do a `watch juju status` and the bundle will update the status
messages with exactly what it’s doing. Keep an eye on IO and cpu usage
while this is happening and if you’re coming from the world of VMs then
prepare to be impressed.

Step 4 - Small tweaks
---------------------

`apt update` and `apt upgrade` can be slow. If you think about it that’s
a bunch of http requests, deb package downloads which are then unpacked,
and then installed in the container. Multiply that *9 times* and
happening *at the same time* on your computer. We can mitigate this by
telling juju to not update/upgrade when we spawn a new instance. Find
`~/.local/share/juju/environments.yaml` and turn off updates for your
lxd provider:

    lxd:
        type: lxd
        enable-os-refresh-update: false
        enable-os-upgrade: false

Since we publish cloud images every few weeks anyway (and lxd will
refresh these for you via a cron job) you don’t really need to have
every update installed when doing development. For obvious reasons, we
recommend you leave updates on when doing things “for real”.

Conclusion
----------

Well, I hope you enjoy the speed and convenience. It’s a really nice
combination of technologies. And I haven’t even gotten to things like
rollback, snapshots, super dense stuff, and more complex workloads. LXD,
ZFS, and Juju each have a ton more features that I won’t cover today,
but this should get you started working faster!

In the meantime here are some more [big data
workloads](https://jujucharms.com/big-data) you can play with. Next up
will be OpenStack but that will be for another day.

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
