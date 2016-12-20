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

Jono [blogged
about](http://www.jonobacon.org/2013/06/17/simplifying-app-websites-with-juju/)
making it easier for people to get up and running with Ubuntu Touch
development. One of the things people always need is infrastructure.

So Marco and I got to work, and made the ubuntu-touch-website kit. The
first in a series of tools that eventually become a stack of deployment
scripts so app developers can get their infrastructure up and running.
So the first easy step is your project’s website. We took heavy
inspiration from [SlateKit](http://slatekit.org/). He just snagged some
Bootstrap and tossed up a site. I’d love a little site like this for all
the new Ubuntu Touch Apps people are making.

Basically, pull a branch, modify a file, run something, and done.

Snag the code from lp:ubuntu-touch-website then modify this config.yaml
file to be about your application. Make sure `python-markdown` is
installed.

<http://bazaar.launchpad.net/~jorge/ubuntu-touch-website/trunk/view/head:/config.yaml>

Now, let’s take that with a little [Bootstrap
United](http://bootswatch.com/united/) and generate the page:

    ./compile -c config.yaml > index.html

And then open the file in your browser. Check it out, and then copy to
your host or cloud bucket. We made it static so it’s easy to deploy.
Read [Jono’s
blog](http://www.jonobacon.org/2013/06/17/simplifying-app-websites-with-juju/)
for what we’d like to do, although currently this just spits out a web
page this is basically a protoype for a Juju Charm so app developers can
deploy more complicated things.

One thing I would like to do is run this by @nathan\_osman and anyone
else who is the kind of person who writes small little apps, what would
you like to see in this kind of the thing? We want to make it quick and
easy. Ideas? We need to add screenshots too.

When you are done the generated page looks like this:

![](http://ubuntu-discourse.s3.amazonaws.com/904f1b7eb73cf5ab54091cbd2699ef966e5c2c7c40.png){width="690"
height="810"}

Some thoughts for ideas:

-   Put the S3 bucket info somewhere so it can just copy to the right
    place and simple serve, this will mean hosting bills in the pennies
    instead of 3 small instances for current Juju until containers and
    colocation land.
-   Is the markdown support really worth the extra dependency? Thoughts?
-   We need to make it so when people want to deploy a blog, a discourse
    forum, a mailing list, etc that this “front page” gets regenerated.

Got any other ideas?

[JOIN THE
DISCUSSION](http://test.ubuntu-discourse.org/t/giving-app-developers-a-quick-start-to-their-infrastructure/405)

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
