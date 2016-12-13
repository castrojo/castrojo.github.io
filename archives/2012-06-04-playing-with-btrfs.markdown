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

I’ve been waiting to try btrfs for a while, mostly to see how it fairs
with other people I know first before giving it a shot. With the release
of the 3.4 kernel I just happened to run into [this
video](http://linuxfoundation.ubicast.tv/videos/btrfs-filesystem-status-and-new-features/)
from Chris Mason talking about the latest things that are going on in
btrfs and I decided to give it a shot. I had also had enough of my
current setup with mdadm and whatever `/dev/md1_127` (or whatever) is
and other weird errors that I got sick of figuring out.

However I didn’t want to risk my existing stuff or try it as the root
filesystem, my use case is more for my home NAS. I got some new drives
for my [HP
Microserver](http://www.jorgecastro.org/2012/04/10/maasing-and-jujuing-with-hp-proliant-micro-servers/)
and got to work. This involved running a pretty [new upstream
kernel](http://kernel.ubuntu.com/~kernel-ppa/mainline/v3.4-precise/),
and building btrfs-tools from git (a straight forward make).

The [btrfs wiki](https://btrfs.wiki.kernel.org) had nearly everything I
needed. I was able to set up a RAID1 of my 4x3TB drives in about … 5
minutes, then mount it. Well, that was boring. No weird devices or
anything, you can just mount any one of the drives in `/etc/fstab` and
it’ll figure out the rest. Nice. I then rsynced everything from my old
system to the new one, which took about 2 full days. While this was
happening it gave me some time to learn about btrfs and it’s commands
and learn about it.

### Things I like

-   I like the RAID/volume/whatever features built into the filesystem
    itself so I don’t have to care about that as a seperate thing.
-   I accidentally made my first cut a RAID10, which is not what
    I wanted. So I changed it RAID1. And it did so. Online. Watching
    this happen live I decided I’m not going back to anything else. :)
-   The commands are very straightforward and make logical sense, so I
    can actually remember them when I need them. This is a place where
    btrfs shines. The technical aspects are cool, but the simple
    attention to UI design is great to me.
-   I have enough free space/drives left over so I can probably live
    migrate to RAID5 when it lands in btrfs in a few kernel releases. I
    am looking forward to seeing this work or blow up in my face. Quite
    interesting!

### Things that confuse me or I don’t like

-   It’s apparently quite difficult to [figure out free
    space](https://btrfs.wiki.kernel.org/index.php/FAQ#Why_is_free_space_so_complicated.3F),
    so I’m using the “add up the drives, figure it out for RAID1, that
    should be close enough” method. At first I didn’t realize a normal
    `df` would lie to me.
-   Obviously no RAID5/6 yet but it’s coming; this is why I went with
    3tb drives for now, despite the expense as I needed as much space as
    my old mdadm RAID5 set up but in RAID1. Prices still aren’t coming
    down to preflood prices so I figure either way I’m going to have to
    bite that bullet.

### Other stuff

It also helps to have a btrfs buddy. I only chose to try this after
Popey and Marco decided they were going to try it too, which is nice to
have someone to ask all the dumb questions. The btrfs wiki is also quite
good, it answered nearly 90% of my questions. At some point when I feel
it’s stable enough for me I’ll repurpose the older drives in my mdadm
array as additions to this filesystem (they are now my backups), which
is quite trivial to do now. On a spare drive in my desktop I
experimented with doing an [on the spot
conversion](https://btrfs.wiki.kernel.org/index.php/Conversion_from_Ext3),
which was quite cool.

I didn’t really notice anything about performance one way or the other.
A home NAS is network limited so I was exercising anything at the
filesystem level as far as I could tell. While other people will be
talking about it’s advanced features I am already a fan for its …
simplicity(!) of usage when managing multiple disks. It also makes what
I used to have to care about not important to me anymore. I’ve already
cleared out all knowledge of mdadm and LVM from my brain and learned
things I actually care about, like snapshots, which I haven’t played
with enough yet.

### So should you try it?

Like with all things if your existing set up is working, don’t mess with
it. If you happen to be building something new then by all means, give
it a shot, even if you end up not using it it’s fun to play with the
commands and learn the new filesystem commands.

There are some risks of course, like running a not-ubuntu-supported
stock kernel; and our kernel team providing fresh upstream kernels means
I can easily upgrade to the new upstream stable releases as btrfs
improvements come out. How comfortable you are with that on your
hardware is up to you. Like all filesystems keep good backups!

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
