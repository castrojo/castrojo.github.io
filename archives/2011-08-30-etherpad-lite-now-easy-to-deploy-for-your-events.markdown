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

[Etherpad Lite](https://github.com/Pita/etherpad-lite) is awesome. Have
you ever organized a conference, large meeting, or foocamp and thought
“wow, I could really have used an etherpad at this event.” But many
times organizers don’t have the resources to get this kind of stuff
running. Now, in an effort to make it trivial for anyone to set up an
etherpad, James has implemented an etherpad lite formula for ensemble. 

Here are the steps. First [install and
configure](https://ensemble.ubuntu.com/docs/getting-started.html)
Ensemble, this is just putting your AWS keys in an environment file
and/or using a PPA if you’re not on 11.10. Then we bootstrap, snag
James’ formula, and then deploy it in EC2.

    ensemble bootstrap
    bzr branch lp:~ensemble-composers/+junk/etherpad-lite
    ensemble deploy --repository= . etherpad-lite

Right now we’re grabbing formulas from Launchpad but in the future that
will be much more user friendly, where you can search for formulas right
from the ensemble command (Like apt-cache search). It takes about 5
minutes to bootstrap, and then another 5-10 minutes to deploy, since
it’s installing everything we need for Etherpad Lite and then installing
it on EC2.

Then let’s check in how that’s going with:

    ensemble status




    2011-08-30 13:24:33,166 INFO Connecting to environment.
    machines:
      0: {dns-name: ec2-107-20-19-203.compute-1.amazonaws.com, instance-id: i-6b706b0a}
      1: {dns-name: ec2-107-20-7-236.compute-1.amazonaws.com, instance-id: i-8f6b70ee}
    services:
      etherpad-lite:
        formula: local:etherpad-lite-5
        relations: {}
        units:
          etherpad-lite/0:
            machine: 1
            relations: {}
            state: started
    2011-08-30 13:24:35,883 INFO 'status' command finished successfully

Ok as we can see there the service has state:started, which means it’s
running. Node 1 is our instance so let’s hit it up, we hit up port 9001
because that’s the Etherpad Lite’s default port:

[\[http://ec2-50-17-151-64.compute-1.amazonaws.com:9001/\](http://ec2-50-17-151-64.compute-1.amazonaws.com:9001/)](http://ec2-50-17-151-64.compute-1.amazonaws.com:9001/)

Neat huh? Ok so I don’t have a fancy URL
like [pad.socallinuxexpo.org](http://www.socallinuxexpo.org/) (Hint hint
Gareth!) but you get the idea. I’ll leave it running for a while so you
can mess with it. When your conference is done, save your data and tear
it all down with

    ensemble shutdown

or keep it around, up to you.

Currently it’s only running in a single instance, there’s no logic in
the formula for load balancing or anything yet, but James tells me it
scales pretty nicely on just once instance. You’ll also note that I
don’t have to know/care about building node.js or npm or any of
those dependencies. The formula author basically does the work for
everyone, ONCE, and then people like me who aren’t familiar with
deploying this sort of app can just enjoy using Etherpad Lite.

Ok so now \$your\_favorite\_event can have an etherpad very easily.
We’ve already made it easy to [get
mediawiki](http://cloud.ubuntu.com/2011/06/so-what-is-ensemble-anyway/),
it’s my hope that eventually we’ll have formulas for every service a
conference would need to get running so they can just fire it up.

This is just an example on the public cloud, later on we’ll show you how
to deploy to bare metal using these exact commands. 

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
