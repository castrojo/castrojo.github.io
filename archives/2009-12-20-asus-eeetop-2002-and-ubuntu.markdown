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

Since Jill started her PhD we’ve been slowly converting the guest room
into a home office. For those of you not familiar with grad school and
beyond, this is basically a room with a computer, a high capacity
printer, and 2,347,345 reams of paper that routinely explode into
mountains of tree-killing mayhem.

She has been comfortable with her Dell XPS 1330, but she’s gotten to the
point where working out of the couch in a laptop is distracting and a
desktop in the middle of a pile of papers started to make sense. I
didn’t want to spend too much, so we decided that a full Ubuntu PC would
meet her needs. I wanted something quiet and sleek, with a webcam and
built in wireless, since I wasn’t about to run a cable up two stories.

After much deliberation I settled on a black friday Amazon deal, \$431
for an Asus Eee Top ET2002 ([video
review](http://www.youtube.com/watch?v=sI7rbHrs0Iw)) with free shipping.
This is an all in one box with a 20” monitor, Atom 330 processor, and
2gb of RAM , and \~240gb drive. This is quite an amazing deal so I went
with it. Having seen one of these at an Ubuntu booth at Ontario
Linuxfest I was confident that everything would just work. Keep in mind
at this price this is the non-touchscreen screen. (EDIT: Correction to
the price, this PC was \$431, not \$331, that would be ridiculous!)

[![](http://castrojo.files.wordpress.com/2009/12/et2002.jpg?w=300)](http://castrojo.files.wordpress.com/2009/12/et2002.jpg)

The hardware is nice, it comes in one box and when it’s set up there’s
only one cable (power) that you need. The out-of-the-box Vista
experience is one of the worst I’ve ever seen from any vendor on any
platform. After the 15-minute “finish the OEM OS install” the vendor’s
next installer comes in, which installs out of date versions of Adobe
Reader, their weird desktop launcher bits, etc. after a reboot it then
goes and updates all that software. After (I kid you not), 45 minutes of
grinding, the computer was finally ready to use. After I got the
hardware info I needed (I could not find any hardware specs on the
internet for the wifi so I had to get it from the PC) I went ahead and
reached for my Karmic CD. This BIOS in the machine didn’t have an option
to PXE boot (which is a shame, it would be a great LTSP client) or boot
from USB so I had to use a CD. The install went off without a hitch.

On boot up I set up her account and added the Ubuntu
[b-sides](https://launchpad.net/b-sides) to take care of the obvious
additions. The wireless was odd, it kept conking out every few minutes
for about 30 seconds. I thought that an updated driver might do the
trick, so I installed the [backported new
wireless](http://packages.ubuntu.com/search?keywords=linux-backports-modules-wireless-karmic-generic)
drivers that our kernel team provides and after that the wireless was
solid. The wireless card is an Atheros AR9285 btw. After that I added
her the PC to the Dropbox account and let it sync overnight.

Some tidbits about the hardware:

-   The Atom 330 - I was expecting a typically horrible netbook
    processor, but this is a really great little chip. It shows up as 4
    CPUs (it’s dual cored and hyperthreaded) and is 64 bit capable. I
    wouldn’t recommend encoding DVDs but for general computing use it
    did the job and I don’t really complain about it.

-   Nvidia ION - Ok, this is fantastic. I’ve switched her over to
    mplayer to use VDPAU and it just cuts through HD like butter. I am
    looking forward to having gstreamer-enabled VDPAU in the future so I
    don’t have to swap the default bits out.

-   Flash - is of course still absolutely terrible. However I found a
    neat
    [plugin](https://chrome.google.com/extensions/detail/kchoimdlcbapmcdnheaahjcdpdjdpfco)
    that replaces the flash on youtube with the h264 file that they use
    for the iPhone and then inlines it in the page with html5 video.
    It’s slick, and more importantly since the ffmpeg in chrome is
    multithreaded it spreads the decoding over the CPU cores, so the
    playback is much, much better than the flash video. I’ve asked fta
    if it’s possible to use the browser’s ffmpeg with a VDPAU backend to
    accelerate this in hardware, but I haven’t gotten too far into that.

-   The hard drive - It’s a pokey 5400rpm drive, was probably used to
    keep the heat down. This kind of makes IO intensive applications not
    very fun to use. Firefox was a grindfest, and OOo is not very fun to
    launch either. However Jill seems to find the OOo performance
    acceptable and I’ve almost completed moving most of her work to
    Google Docs anyway.

-   Amazon MP3 in 64 bit was annoying to fix, I used some work around on
    the internet I am not proud of, however I hope to transition to the
    Ubuntu One music store when it is available. Striving to keep with
    as much a default install as possible I left Rhythmbox on there
    for her. Her G1 is detected and syncs as expected.

-   The mouse - it’s kind of crap so I replaced it with one she uses for
    her laptop. In case you’re wondering the colored keyboard in the
    picture is a [gboard](http://gboard.com), which is a dedicated
    keyboard for Gmail that the manufacturer sent me to test how well it
    works in Linux (it works great and ootb with 0 config by the way).

-   Suspend and Resume just work, I have it set up to suspend when you
    hit the power button.

-   The Camera works great:

[![](http://castrojo.files.wordpress.com/2009/12/cheese.jpg?w=300)](http://castrojo.files.wordpress.com/2009/12/cheese.jpg)

All in all, I think the ET2002 is a great little box, especially for the
price I got it at! On some days I go up there and work out of her office
and have no problems getting work done. I am mulling replacing the pokey
drive with a cheap SSD for noise,heat, and performance win, but this
isn’t the kind of machine that has easy to see drive bays or things of
that nature so I don’t know if I want to take it apart. The speakers
aren’t amazing but good enough to listen to music while working.

I only wish that there was an option for Ubuntu out of the box on an
all-in-one so I wouldn’t have had to spend 2 hours making it work
better. I think system76 should take the guts of the
[meerkat](http://system76.com/product_info.php?cPath=27&products_id=91)
and put together something just as compelling! If you’ve seen these with
the touchscreen and Ubuntu Netbook Remix (now the Netbook Edition) then
you know how cool it can be with the touch stuff.

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
