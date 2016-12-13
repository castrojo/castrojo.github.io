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

Yikes, quite a statement!

For the past 6 months we’ve been [travelling
around](http://juju.ubuntu.com/Events) conferences talking about
[juju](http://juju.ubuntu.com) and
[charms](http://juju.ubuntu.com/Charms). We’ve had charm schools and
training events, but it’s been difficult to explain to people the
differences between service orchestration and configuration management,
especially with a tool that wasn’t so complete. Thanks to the work for
some volunteers though, we’ve managed to have 58 charms available in
Ubuntu so far.

But to you that means nothing because we haven’t made it easy to get
this stuff, until now. Today the juju charm store landed and it will
monumentally change the way you use Ubuntu Server in 12.04. Now that
this is in place I can hopefully show you by example on why juju is
awesome.

In this post I want to talk more about policy than juju itself. If
you’re on precise these commands won’t work (since we haven’t deployed
the charms to Precise yet), and our docs aren’t quite up to snuff yet,
and two of the commands I talk about don’t even exist yet. So instead of
following along try to envision what we’re trying to accomplish
policy-wise:

You start by [picking a service](http://jujucharms.com/), and then
deploying it:

    juju bootstrap
    juju deploy zookeeper
    juju expose zookeeper

juju goes off and fires up an instance, installs zookeeper, and
configures it. I don’t really have to care about things that aren’t
important to me like finding what image to deploy, provisioning the OS,
or that kind of thing. And if I do we make it easy in
`.juju/environments.yaml` for you. Fire up `juju status` and wait until
you see the public IP of your service, then it’s all done. You see up to
now that didn’t work, we made you manually branch things and stuff. But
that’s not even important right now, the big change here isn’t the
addition of juju itself, it’s the charm store.

The new new archive
-------------------

One of the best things about apt has nothing to do with apt itself.
There’s been other tools that do the same thing, but nothing like apt.
Why is that? Because while apt is great, you don’t really care about
apt, you care about *the archive* at the other end of apt. That huge
collection of software. But sometimes it can be limiting. While we love
the convenience of a stable archive, it can slow us down, especially
when trying new technology, and doubly so in the fast paced world of the
cloud. Right now the version of zookeeper in 12.04 is 3.3.5. Normally we
would have that for the next 5 years. We have PPAs, but you have to know
where to find them, and that’s only half the battle. There’s more to
services than just packages. And what about other services? Why isn’t
this just built into the OS?

Well, with the juju charm store we can have our cake and eat it too.
It’s a collection of charms (scripts) that we can use in Ubuntu. Let’s
rewind and instead use this command:

    juju deploy zookeeper
    juju set zookeeper source=dev
    juju expose zookeeper

That did exactly what you think it should do. We installed the
development version of zookeeper. Why? Because the charm author made it
so on install you could install from the Ubuntu archive, or from a PPA.
If he wanted to he can grab the pure upstream source, or pull right from
the VCS and expose that as an option.

Wait what?
----------

PPA’s were the first step. But there’s no structure there, and that’s
only about packages. Huntin’ and peckin’ for repositories. Boo. Here’s
why this works:

-   In the charm store, we allow a charm to deploy a service *however
    the author chooses*, with some caveats (see below).
-   We don’t freeze the charm store. It’s a living archive that can be
    as up to date as people want it to be.

This is a monumental addition to Ubuntu. Anything in the juju charm
store can be deployed and updated for the life of the release. Sick of
searching for “How to deploy node.js on ubuntu?” and finding some guy’s
script on a pastebin? We have a charm that does that. Right now it uses
Chris Lea’s PPA to install node. Because that’s what everyone is doing
anyway. So if this is *the way* the community is deploying node on
Ubuntu then we’re going to say “okay! but let’s organize this.”

In fact, those scripts you see on pastebins are the first steps to
getting those services charmed. So why put them in a store?

-   Community peer review. The store is designed to be shared and for
    you to modify stuff and push it out to people.
-   Being in the store puts you closer to your end users, no more
    deployment scripts on wiki pages!
-   We run automated testing on the charm store and spit out warnings if
    your stuff breaks.
-   Since juju is service orchestration in the store runs on EC2,
    OpenStack, and bare metal. Test on your laptop and *know* it’ll
    deploy on OpenStack.

Since the store isn’t frozen, next year the nodejs charm will get you
what you want, you’re not stuck with what’s in the archive now forever.
Will the PPA move? Will people want to install node another way? We
allow the community to update the charm to be whatever is the current
state of the art. And not just nodejs. Whatever service anyone has a
charm for.

But I don’t know anything about packaging
-----------------------------------------

Packaging can be hard. I can think of countless projects off the top of
my head that have their own deployment scripts, or a list of
instructions on their wiki page on how to get something installed. We
can gather all of those and put them in the charm store. Take your
deployment script (in whatever language you want), submit it to the
store, and your software is ready to go. We can build on top of other
charms:

    juju deploy -n3 mongodb # We’d like a MongoDB replicaset, 3 nodes please!
    juju deploy --config node-app.yaml node-app # Then deploy my node application from source using the node-app charm with config information
    juju add-relation mongodb node-app # Hooks fire off and my application now talks to the mongodb replicaset
    juju expose node-app # Open the port, serve my app! 

What if every node.js application was deployable this way? Rails.
Whatever you’re into. All of it. *That* is what we’re building in the
juju charm store, the ability for people to do just that. All of a
sudden if your project isn’t in the Ubuntu archive you can still reach
your users. Publish your charm after the release is already out and keep
it up to date. We move out of the way and give you a solid OS; *you*
deploy the stack you want how you want it. Wouldn’t it be great then if
we could:

    juju publish # But we don't have this yet.

So for that part you’ll have to push a branch, but you can see where we
want to go. And then your application is available via
`juju deploy ~yourname/yourapp`. Submit it to the store, get it
reviewed, and it becomes `juju deploy yourapp`. It’s not so much about
juju itself as it is about having a place where devops can collaborate
around services.

Be in control of your own platform and share by default
-------------------------------------------------------

Our default charms are pretty conservative. In fact, the charms you’ll
be able to deploy with the default deploy command are generally boring
right now. But maybe you don’t care about running zookeeper from the
archive, you can have your charm grab the tarball, install the
dependencies you need, and build it right on the spot.

Maybe your charm grabs your source from github and runs it right out of
there. Totally fine. We just tell you to put it in a certain place.
Don’t like how James deploys zookeeper in his charm? Okay:

    juju source zookeeper ~/my-local-version   # We don't have this yet either, you can just pull from VCS for now
    cd my-local-version # and then make your changes
    juju publish # But we don't have this yet, so you'll have to push somewhere.

And now users can `juju deploy cs:~yourname/zookeeper` the way you like
it. That’s it.

And not just you as a person. How about your projects? Look at the
instructions for Ubuntu users on the [Varnish home
page](https://www.varnish-cache.org/installation/ubuntu):

> Varnish is distributed in the Ubuntu package repositories, but the
> version there might be out of date, and we generally recommend using
> the packages provided by varnish-cache.org.

There you go. This project has just told us the very first thing a
varnish charm should do. We don’t have one yet. Are you deploying
varnish to the cloud? That script you’ve been using to do all this sort
of stuff, that’s the beginning of a charm. Did I mention you can write
them in whatever language you want?

Caveats and Unicorns
--------------------

However, we’re not hosting an intergalactic kegger here, we’re not going
to allow charms to do bad things. We have some policies in place in the
official part of the charm store, you can [see them
here](https://juju.ubuntu.com/Charms). I won’t go into each one here,
but the idea is like the Ubuntu mindset “Be nice, be collaborative.” and
then some technical checks to make sure it works, things like
idempotency, the right to distribute, etc. The peer review in the charm
store will be a fun and loosely coupled process. We’ve got 58 charms
right now. We’ve got some big holes to fill in.

The juju community have stepped up to the plate and have nailed some
useful ones like Hadoop, Cassandra, MongoDB, Jenkins, MySQL, PostgreSQL,
lodgeit, OwnCloud, ThinkUp, Alice and Subway IRC, TeamSpeak, phpMyAdmin,
and even an entire PaaS in CloudFoundry. We even have game servers like
Minecraft and Steam. The bits are in place, and now we’re ready to grow
this.

So while I think you can have your cake and eat it too, this is only the
first step. We think we have a compelling story to tell here in the
cloud, where you can quickly deploy, manage, and share with others. We
have some serious barriers to overcome, juju is just getting started,
and as you can see when you play with it, there’s still some rough edges
and limitations we need to work out, but we have a crack team of folks
working on this and we’re ready for people to start kicking the tires
and giving us feedback.

But while we’re working on baking as many cakes as we can, but like many
things in open source, the ecosystem of cakes is what makes it great, so
if you want to deploy on the cloud we’re working hard to eliminate
deployment barriers for you, I hope you [join
us](https://juju.ubuntu.com/Charms)!

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
