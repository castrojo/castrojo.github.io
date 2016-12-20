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

We’ve had a [breakneck pace](http://jujucharms.com/recently-changed) of
Juju progress over the past few months, I’m going to attempt to
summarize all the fabulous work the Ubuntu community has been working on
to make deploying applications in the cloud a rockin’ experience.

The Node.js, Django, and Rails charms are what we call “platform
charms”. The idea here is to whip up a quick config telling juju where
your application lives (github, etc.), then you just pass that along to
juju and it’ll deploy your app in the cloud. Check [this
out](http://www.jorgecastro.org/2012/11/16/deploying-your-rails-application-in-the-cloud-via-juju/)
for an example. Ideally with these charms we can make *any* applications
written in these stacks to be instantly deployable with little to no
work by the user.

### Node.js {#nodejs}

-   Marius B. Kotsbak has been working on our Node.js charm. His first
    is to add [support for
    updating](https://code.launchpad.net/~mariusko/charms/precise/node-app/trunk)
    the user application.
-   Marius has a
    [blueprint](https://blueprints.launchpad.net/juju/+spec/juju-charm-app-git-deployment)
    with how he expects the node charm’s behavior will be fleshed out.
-   Feel free to ping Marius or myself if you’re a node.js developer and
    interested in helping out.

### Django

-   Patrick Hetu and Bruno Girin have been on a roll lately, check out
    [this
    post](https://groups.google.com/d/msg/django-users/979lJojyxs0/KK9fWfkK0FYJ)
    to the django-user’s mailing list asking for feedback on their
    Django work.

### Rails

Lots of activity in Rails this week, thanks to Pavel Pachkovskij from
[Altoros Inc.](http://altoros.com/)

-   A [Rack charm](http://jujucharms.com/charms/precise/rack) that let’s
    you deploy a rack application.
-   And you have your choice of which webserver you want to deploy with
    it, either
    [apache2-passanger](http://jujucharms.com/charms/precise/apache2-passenger),
    or
    [nginx-passenger](http://jujucharms.com/charms/precise/nginx-passenger).
-   And lastly (not in the store yet), there’s an addition of the [God
    monitoring
    framework](http://jujucharms.com/~pavel-pachkovskij/precise/god),
    which you can use as a subordinate charm to monitor your
    deployed stack.

Not a bad set of updates for Rails, we’re hoping that by 14.04 we’ll
have a fully instrumented Rack stack that will be tested and scalable
for everyone.

### Databases

-   Stuart Bishop has added master/slave replication to the
    Postgres charm. You can find out how to use it in [the
    README](http://jujucharms.com/charms/precise/postgresql).
-   Antonio Rosales demoed setting up replicasets with the [MongoDB
    charm](http://jujucharms.com/charms/precise/mongodb) at
    MongoDB Austin.

### Other updates

And those are just the highlights, a ton of work continues to go into
one of our most important set of charms, OpenStack, too many to list
here, we’ll just show you at ODS, heh.

-   What will become Juju 2.0 has now released version
    [1.9.11](https://lists.ubuntu.com/archives/juju/2013-March/002156.html)
    for your testing pleasure, this is the first time the 2.0 series can
    run on HP Cloud, so we could use some testing there.

Come check us out at [any one of these events in
2013](http://juju.ubuntu.com/Events) if you’re interested in learning
more.

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
