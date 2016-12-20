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

Last time I was looking for a laptop I [chose the hp
2510p](http://stompbox.typepad.com/blog/2007/10/on-portable-lap.html).
The 2510p is a great laptop and I will continue to use it. Unfortunately
the pokey 1.8 inch drive in it was really starting to annoy me, so I
decided to look for a new laptop, something that would be able to churn
through VMs and the like.

Ok, I lie … I didn’t /need/ a new laptop that bad, but as many of you
know, I am a Thinkpad junkie and I just couldn’t bear to not have one,
so I got a new Lenovo X200. Pics
[here](http://picasaweb.google.com/jorge.castro/ThinkpadX200). I’ve had
it for about a month and thought I would share my opinion of this
laptop.

First things first. I decided to skip the fingerprint reader this time
around because I found myself never using it in my old laptop. It only
comes with Intel video so that was an easy decision, for wireless I
opted for the Intel 5300. Unfortunately for me Lenovo instead sent me an
Intel 5100 wireless adapter in the X200. I was wary of the 5100 due to
it’s apparent
[regression](http://www.anandtech.com/cpuchipsets/intel/showdoc.aspx?i=3356&p=6)
in performance vs. a 4965. I haven’t had any issues with the 5100 other
than the feeling in the back of my head that I should have gotten a
5300. I could just mail Lenovo but I didn’t want to ship my laptop back,
and I wonder if they would even just send me the 5300 in the mail so I
can install it myself. Either way wireless isn’t an issue with this
laptop in Ubuntu.

[![](http://lh4.ggpht.com/_1Thkya8n93k/SQx_er25UAI/AAAAAAAAHwg/T5sJsBwyaxg/s400/image153.jpg)](http://picasaweb.google.com/lh/photo/UEDkh1xcOuzTW0Y43U1GBA)

From
[ThinkpadX200](http://picasaweb.google.com/jorge.castro/ThinkpadX200)

Installing Ubuntu
-----------------

Thanks to evand’s awesome
[usb-creator](http://en.wikipedia.org/wiki/Usb-creator) I was able to
make a USB stick installation on my desktop in a few minutes and then
installed Ubuntu 8.10 via USB. I am really starting to prefer this
method of installation because it’s easy, doesn’t need a CDR, and best
of all, it’s quicker.

Initial X configuration was kind of borked - I was seeing [bug
273899](https://bugs.edge.launchpad.net/ubuntu/+source/xserver-xorg-video-intel/+bug/273899).
After finding information from the
[thinkwiki](http://www.thinkwiki.org/wiki/Installing_Ubuntu_8.04_&_8.10_on_an_X200)
and the always excellent [Ubuntu
Forums](http://ubuntuforums.org/showthread.php?t=907936&highlight=x200)
I was able to find a xorg.conf that did the trick. Chris Jones also
happened to have an X200 handy and added some information to the bug.

Suspend and resume was fixed by adding a acpi\_sleep=s3\_bios to the
kernel boot parameters. I also followed the thinkwiki recommendations
for BIOS settings.

The webcam was also not working in Cheese, see [bug
290506](https://bugs.edge.launchpad.net/ubuntu/+source/cheese/+bug/290506)
and [bug
287888](https://bugs.edge.launchpad.net/ubuntu/+source/linux/+bug/287888).

The fan sometimes goes nuts and thinkwiki recommends this thing called
tpfand. I did not try this because Chris Jones recommended not to have a
userspace daemon to control the fan. I don’t know jack about things like
this so I just let it go crazy, I suppose it’s better to have it on than
having it shut off and overheat the laptop. New thinkpads have
redesigned fans so even when it’s at maximum I can barely hear it

I will be following up on the X bug and the fan thing with the
appropriate people at the Ubuntu Developer Summit.

The X200 itself
---------------

I was attracted to the X200 because it is much cheaper than the X300,
which is a tad large for me anyway. I purchased it with 1GB of RAM and
will likely bump it up to 4GB prior to UDS. (I usually don’t max out RAM
from a manufacturer because their prices are usually terrible). I didn’t
go with an SSD because it was an extra \$600 and I would rather wait
another 9 months now that Intel has upped the ante with their SSDs.

I’ve owned an X40 in the past and the X200 is a “widescreen version of
the X40/X60”. However it does feel bulkier than I think it should, it
feels more like a smaller T series than a widescreen X. Still it is
quite small and compact though.

Build quality is what you expect from a Thinkpad, it’s a tank. I have no
qualms about grabbing it from the top of the screen and moving it around
(something I wouldn’t do on Jill’s M1330). The keyboard is what you
expect of a Thinkpad, nearly perfect. I wish they would fix the F1/ESC
thing though, it’s annoying for vim users. The Fn/Ctrl order is
different from the hp, so I have to get used to that. I have 3 beefs
with the hardware:

-   As you can see with the pictures the bezel on the top of the LCD is
    real thick. Too thick.

-   Two of the USB ports are toward the front of the machine, making the
    “sitting on the couch with a USB key plugged in” use case kind of
    scary for me. I much would have rather had the USB ports in the back
    or more towards the rear of the case.

-   No LED backlight. That’s right; my hp 2510p is a year older and has
    an LED backlight; this option is only available on the X300. Boo.

Battery life so far has been a tad over 5 hours. Note that I usually
don’t dim my display when on battery and I also haven’t gone through the
powertop recommendations as of yet. Performance is excellent (I got the
C2D 8600, 2.4ghz), but like I mentioned above I have not maxxed out the
RAM so I can’t say anything about VM performance just yet. The 160gb
7200rpm drive is quick, no issues with it so I suspect it will run
multiple VMs fine. Heat dissipation is great, it doesn’t get warm or
uncomfortable.

Overall I’m very happy with the X200 and I recommend it. Like all new
notebooks there can be some gotchas as far as hardware support in Linux
goes, but that usually works itself out after a release. Many thanks to
the Thinkwiki and Ubuntu contributors who have documented the quirks and
reported bugs.

Blog note: I have no idea why planet keeps bumping my Banshee entry to
the top of planet, I promise I am not doing it on purpose, heh.

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
