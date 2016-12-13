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

I [recently
blogged](http://www.jorgecastro.org/2012/03/18/redeploying-omg-ubuntu-onto-the-cloud-with-juju/)
about how we redeployed [OMG!Ubuntu](http://omgubuntu.co.uk) onto AWS
with juju and Ubuntu Server.

But as I talk about in that post, I had made the mistake of “it’s not
optimized, throw hardware at it!” and left the site up running on 4
extra large amazon instances. As Marco worked on the charm and Clint and
I talked about how to move forward I kept kicking myself for going so
overboard. Then Clint explained to me how the cloud lets you
overcompensate, and then optimize, deploy, optimize, deploy, and so on.
Each time cutting down on resources and saving money.

Here’s how we did this part with juju.

Capture your expertise
----------------------

First things first. How did we fix the Wordpress charm? Well, Marco
analyzed everything we needed, branched the old one, and [created
this](http://charms.kapilt.com/~marcoceppi/oneiric/omgubuntu-wp). Click
on all the hook links on that page to see what the charm does. I’m not
going to go into every detail here, but the basics are, we pull
Wordpress from upstream now to get the latest version, and the 2nd major
thing is we implemented [Brandon
Holtsclaw’s](http://blog.brandonholtsclaw.com/) nginx configuration and
heavy caching. It was important for us to capture every improvement, so
we don’t have to do it again. This can be tough when firefighting, the
temptation to just ssh into the node and fix it on the spot was a
tempting carrot for most of this. But, determined not to do work over
and over, we kept improving the charm.

We are now running on 3 mediums for wordpress, all load balancing
between themselves via nginx, and then one small for mysql and one small
for juju’s bootstrap node. Ryan Kather asked why we weren’t using Amazon
Elastic Load Balancing, but it turns out that ELB needs a DNS change and
we don’t have access to DNS when Joey is asleep so we just decided to
have nginx do the load balancing. Since nginx is doing that we don’t
need ELB and we certainly don’t need an instance for haproxy.

Now that the site is up (and still overkilled) we created a
staging.omgubuntu.co.uk. And then (this is the cool part), Marco
redeployed the charm again but on t1.micros. Now we have the exact
deployment but on smaller machines so we can optimize.

And then iterate again and again
--------------------------------

Each improvement gets pushed to the charm and redeployed. On the public
cloud for a site the size of OMG! it takes 7 minutes to deploy. That
means we can work on the charm and test it on staging quickly. If Clint
wants to iterate even quicker he can just [deploy on his
laptop](http://askubuntu.com/questions/65359/how-do-i-configure-juju-for-local-usage)
until he’s ready, and then push to AWS.

This enables us to tweak staging and then when we’re ready either
upgrade those micros or redeploy to something bigger. Right now the load
on each medium instance is about .05, so we can now start to pare down
the instance size to smalls so we can be more elastic in growth. Again,
still overkill but since it’s so easy to test we can do this relatively
quickly. I suspect our goal of getting down to 2-3 smalls is still
easily attainable.

### Some tools and other lessons we’ve learned:

-   siege (it’s in the archive), lets us load test on the deployments to
    see how they perform
-   [blitz.io](http://blitz.io/) is hosted siege that let’s you test
    from multiple locations.
-   [nginx](http://nginx.org/) in the hands of someone like Brandon is
    really epic.
-   We fired up a micro with byobu and then the team juju’ed in there,
    so we could collaborate in real time.

### And some things to fix

-   We’re caching so hard if he posted right now it would take an hour
    for it to show up on the site, so we’re still figuring out how to
    have a post cache refresh happen when he posts.
-   Brandon wants to investigate
    [Cloudflare](http://www.cloudflare.com/). He’s used it in the past
    and likes it so we’re going to play with it.
-   We’ll need to branch and generalize and “backport” this set up to
    the Wordpress charm in the charm store. I am now convinced that this
    set up (and variations the community comes up with) should be the
    way we deploy Wordpress in Ubuntu, it will be exciting to see people
    deploying their blogs this way.

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
