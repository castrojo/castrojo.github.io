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

Well it’s another cycle and another Ubuntu release and it’s another
cycle’s worth of Charm Store improvements. Since the [Charm Store
doesn’t
freeze](http://www.jorgecastro.org/2012/04/03/the-juju-charm-store-will-change-the-way-you-use-ubuntu-server/)
we can continually improve the capabilites of the charms over time while
users can stick to the stable userspace that 12.04 LTS provides.

If you’re new here and have no idea what [Juju](http://juju.ubuntu.com)
is then check out [the
video](http://www.youtube.com/watch?v=1yoIdgdqzLk&feature=player_embedded).
And what are charms? Well charms are the services you deploy. If juju is
apt-get for the cloud, then charms are the packages for those clouds.

Juju has one mission in life, and that’s getting your services not only
deployed, but manage them over the course of their lifecycle. Our job is
to take your code and get you up and running on AWS, HP Cloud, Azure,
and OpenStack as easily as possible.

First the raw numbers
---------------------

-   133 [peer-reviewed charms](http://jujucharms.com/charms/precise) in
    the store
-   288 charms in personal branches
-   151 total contributors (82 Canonical, 57 non-Canonical, 12 Canonical
    Juju coredevs)

As far as raw Charm download numbers, these are currently unavailable to
browse, however next week or so when the new GUI/website land users will
not only be able to see the number of downloads per charm, but if the
charm works on a given provider. More about that in a future blog post …

So what’s in the app store?

Rails, node.js, and Django {#rails-nodejs-and-django}
--------------------------

One term you might be hearing tossed around is “PaaS on my own terms”.
The idea here is that people really like the workflow that you can get
with Heroku and other PaaSes, but don’t want the added complexity. Just
your app and your provider.

Here’s how it works… assuming your Rails app is “myapp”, let’s deploy
your application with postgresql to show you the kind of workflow we
provide. We provide generic “platform charms” that let you snag things
right out of version control and deploy them. Assuming you have a
myapp.yaml file describing your application:

    myapp:
      app_name: myapp
      repo_type: git
      repo_url: "https://github.com/mmm/testrails.git"

Now you’re to deploy on your cloud provider, this can be AWS, HP Cloud,
your own OpenStack, or your local Ubuntu laptop:

    juju bootstrap  
    juju deploy --config ~/myapp.yaml rails myapp
    juju deploy postgresql

relate them

    juju add-relation postgresql myapp

open it up to the outside world

    juju expose myapp

Find the myapp instance’s public URL from

    juju status

Like all services that can connect to a reverse proxy, we’ve made it so
that you can easily scale out your application horizontally via haproxy:

    juju deploy haproxy
    juju add-relation haproxy myapp
    juju add-unit -n5 myapp
    juju expose haproxy  # Change your DNS to point to this IP instead
    juju unexpose myapp  # We’re behind haproxy now, no need to leave this open to the world. 

And this is just the rails example, we can do this for node.js and
django, and I’m always keeping an eye out for Java-smart developers, so
if you want to make this kind of workflow for your platform, let me
know!

Databases and other infrastructure
----------------------------------

Need master/slave with that Postgres? We’ve got it, you just need to
fire it up with [a few
commands](http://jujucharms.com/charms/precise/postgresql).

Any Ubuntu user can set up a master/slave Postgres setup this way. It’s
nice, it’s like having Stuart Bishop and his roving band of IS
Postgresql gurus setting up your Postgres config for you. And since we
dogfood OpenStack and our charms everyday, it’ll work.

Need to set up replicasets in MongoDB? We’ve got that built into the
[MongoDB charm](http://jujucharms.com/charms/precise/mongodb) too.

Or sometimes you just need a [blank LAMP
stack](http://www.jorgecastro.org/2012/10/10/a-blank-slate-for-lamp/) or
you can toss in some
[elasticsearch](http://jujucharms.com/charms/precise/elasticsearch) if
you want it.

Come see us and tell us what you need
-------------------------------------

Come check us out at [any one of these events in
2013](http://juju.ubuntu.com/Events) if you’re interested in learning
more or join us at our next [virtual Charm
School](http://www.jorgecastro.org/2013/04/24/join-us-for-a-virtual-charm-school/).

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
