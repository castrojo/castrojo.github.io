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

One of the nice things about the cloud is being able to horizontally get
what you want, as long as you either have servers on the other end or a
wallet if you don’t.

I’ve always dug projects like [BOINC](http://boinc.berkeley.edu/) and
folding@home. And of course, our never ending [search for
ET](http://setiathome.berkeley.edu/). To me the best part is of course
the leaderboards on how you’re competing with everyone else. Look at
[this
subforum](http://arstechnica.com/civis/viewforum.php?f=18&sid=6db63962fd1fa61f6107f2e015ca7879)
on Ars Technica as an example.

“But what if I could just rent enough public cloud capacity to pass my
smug competition? In the name of science of course.”

Well, let’s see, we do have HVM Compute Cluster AMIs for Ubuntu. You can
just search for “hvm” in our [handy dandy AMI
browser](http://cloud.ubuntu.com/ami/). These instance from Amazon can
be [pretty performant](http://aws.amazon.com/hpc-applications), and even
offer GPU crunching. But at \$2.40 an hour, too rich for my blood.

However if you look at the spot instances of the Eight Extra Large,
right now it’s at 56 cents. Now this is much more interesting, I wonder
how much bang for the buck I can get out of this. But I don’t want to
spend too much (yet).

> I saw a six pack of soda-pop for \$1.20. That price f—s with your
> head, man. Because then I though that I would start selling soda-pop.
> Suddenly I got things of pop with me. “What’s going on, Mitch.” “Not
> much, looking to buy some pop? Fifty cents a can. It’s not
> refridgerated because this is a half assed commitment.”
>
> **Mitch Hedberg** Comedian

Hmm so maybe I don’t even need the computing instances, if it’s just CPU
bound then maybe it’s not worth the extra cost for all the other high
end things those instances provide. Or I can at least estimate my
price-performance ratio with whatever BOINC project I am interested in.
Either way I think it would be cool if we had juju charms for these
projects so that people can experiment with deploying all these
interesting scientific things on the cloud in an easy way. People are
already running [BOINC on
EC2](http://boinc.berkeley.edu/wiki/Installing_BOINC_on_EC2), but with a
charm we can just have it in Ubuntu out of the box, no need to have
someone maintaining a separate AMI for this when we can just have it.
And with juju and config options in charms we could just control the
clients through the same interface that we can control any other juju
service. And of course, since it’s in the charm store it means we can
deploy on bare metal and OpenStack. What a nice way to break in all that
shiny new hardware.

So I’ve filed two bugs, one for
[BOINC](https://bugs.launchpad.net/charms/+bug/943481), and one for
[Folding@home](https://bugs.launchpad.net/charms/+bug/943505). Bruno has
snagged BOINC as he plans on entering it in the [Charm
Contest](http://cloud.ubuntu.com/2012/02/juju-charm-contest-help-bring-free-software-into-the-cloud/),
but folding is still up for grabs.

Though the projects in BOINC and FAH are relatively familiar to us I
think it’d be interesting to think of all the HPC software that is out
there that needs computing power and how you can tie that into an easily
deployable juju charm. Spot instance price just drop and make renting
out the time economically valuable for you?
`juju add-unit -n50 myproject`. Prices go up?
`juju remove-unit -n50 myproject`. Your funding finally come through for
your own resources? Redeploy locally. Or start locally and scale up on
the public cloud based on what you need.

Are there other computational tasks you think can be deployed this way?
Let me know in the comments, or feel free to charm it up and submit it
to the [juju charm
contest](http://cloud.ubuntu.com/2012/02/juju-charm-contest-help-bring-free-software-into-the-cloud/).

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
