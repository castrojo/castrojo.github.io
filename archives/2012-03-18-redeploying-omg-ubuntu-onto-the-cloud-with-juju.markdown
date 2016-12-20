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

On St. Patrick’s day [Marco Ceppi](http://marcoceppi.com/) and I were
chatting about SPDY. I was wondering if we could make an option on the
WordPress charm to try the experimental SPDY support in either Apache or
some other web server. It’d be a cool trick. In general the WordPress
charm is boring and generic, it needs to be
[hotrodded](http://www.jorgecastro.org/2012/02/09/shipping-best-practice-with-juju-charms/).

Then we noticed OMG!Ubuntu was still down. He had moved his server and
all it was returning was a “It Works!” page. As we talked about the
charm I kept following the gnashing of teeth from Ubuntu fans aching for
their news. Moving a server. Takes a weekend? Over 3 days of downtime?
Then it just started to really bother me.

This is 2012, we’re smarter than this! So I asked Joey if we could help.
Some standalone server being set up in some rack on only one box? What
happens when the site gets busy? What if the facility goes down? So
we’re not only going to move him to AWS, we were going to do it with
juju so we can show people how easy this is.

Challenge Accepted.

Step One - Think about how you want to be. {#step-one---think-about-how-you-want-to-be}
------------------------------------------

Let’s get started then. I know we’re going to use juju, so:

    juju bootstrap

And a node fires up on AWS and starts configuring itself with Ubuntu
Server. I know we will want a three tier system. One MySQL, one for
WordPress, and one for a load balancer so we can add more WordPress
later.

    juju deploy wordpress
    juju deploy haproxy
    juju deploy mysql

Three more instances fire up, with Ubuntu Server, and start installing
all those things. Ok, now let’s introduce them. HAProxy needs to know
where WordPress is, and WordPress needs to talk to MySQL.

    juju add-relation haproxy wordpress
    juju add-relation wordpress mysql

This is where the magic comes in. The hooks know what WordPress should
do when it talks to haproxy, and what to do when talking to MySQL. Ok,
we’re done, we have Wordpress ready to go. Not bad, 7 commands to a
brand new OMG!

I then did a `juju expose haproxy` and told Marco “Ready”. I had shared
my juju environment with him and put both of our ssh keys in it. Because
of this I was able to type these commands and Marco could run
`juju status` and check on them. After about 9 minutes or so for the
instances to fire up he was ready to go and we had WordPress up.

Step Two - Getting your old stuff
---------------------------------

Joey provided Marco with access to his server with the wonderful
`ssh-import-id` tool. All he needed to do was `ssh-import-id marcoceppi`
and the tool went to launchpad, grabbed his ssh keys, and added them to
the server. Then Marco was able to ssh in and copy the data.

The first set was the MySQL dump. He can get to the MySQL node by just
doing `juju ssh mysql/0` and to the WordPress node with
`juju ssh wordpress/0`. This copy took a bit, the MySQL database was
only about 750MB compressed, but there were like 3GB worth of images.

Since this was a WordPress install the only directory that need to be
moved was `wp-content`, this made updating simple with the exisiting
charm and WordPress infrastructure.

Step Three - Getting it all ready to go. {#step-three---getting-it-all-ready-to-go}
----------------------------------------

Marco copied all the WordPress files in the right spot while I
refreshed. And … it worked! Almost. Some images were missing. They were
still on the old server, just in a spot we weren’t expecting. Easy fix
to copy them over.

We banged on it a bit and we were good to go!

Step Four - Let’s do it. {#step-four---lets-do-it}
------------------------

Right around here I realized I had made a mistake. We had initially
started with 4 small Amazon instances. Redirecting the traffic from the
old server just for a few seconds crushed the instances. The load on
WordPress was 90 alone. Ah nuts I said, should have gone large. I
specified extra large in the juju config and reran those commands. When
the new environment was up Marco was able to copy the data over to them.
Since we were already on AWS instance to instance copy was at LAN speed.

Then we pointed traffic at it again. Instances got smoked again. This
time the load was around 40. How? How can one blog smoke these instances
like that?

Step Five - Expertise, there is no replacement. {#step-five---expertise-there-is-no-replacement}
-----------------------------------------------

I texted Ubuntu Server Engineer and MySQL ninja [Clint
Byrum](http://fewbar.com/) and explained the situation. He checked it
out and had it humming in about 5 minutes. So much so that he finished
with “Hey you could have just run this on an m1.small, did you guys try
that?” Thanks Clint. Now all that was left to do was getting the
WordPress node under control.

Marco did this a few ways, he turned on Caching in WordPress, and added
Opcode caching in php with APC. Eventually the load on the WordPress
instance went down to .01. There were some additional issues with the
sheer amount of WordPress plugins OMG! is using, which makes it hard to
debug what was going on.

By now Joey was long asleep, we were about 5 hours in, but it was FAST
on AWS. So we sent him a mail with the elastic IP so he could move DNS
and went to bed.

And where the big work begins. {#and-where-the-big-work-begins}
------------------------------

Right now the site is running on 4 extra large AWS instances. This comes
out at about \$3.56 an hour + bandwidth. Not ideal, especially since we
know we can move back to m1.smalls. We learned a bunch, in fact, it
brought to light some things we can fix in Ubuntu:

-   The first trick will be to move the images to S3 buckets. Right now
    the WordPress EC2 instance is serving the images via Apache. This
    is expensive. We can move these all into S3 buckets and ~~save way
    more money~~ pay the same amount of money but take the load off the
    WordPress instance so won’t even have to be so busy, we can move
    that to an m1.small. (Update: I was wrong on EC2 and S3 pricing for
    outgoing data, current 12 cents a gig for either one.)
-   We can also move MySQL to an m1.small.
-   haproxy just points people around, we can move that to an m1.small.
-   And lastly we can move the juju bootstrap node to an m1.small.
-   The WordPress and MySQL charms need work. They basically just
    apt-get install stuff and connect them to each other, they don’t do
    what people need for them to do to deploy a real site. This helps us
    a bunch, but it would be wicked to have experts collaborating around
    this work. It wouldn’t hurt to make the MySQL package more scaleable
    out of the box either.

Doing this will make OMG! run on 4 m1.smalls, .32 cents an hour instead
of \$3.56; plus bandwidth costs. We can cut down a node soon when juju
supports putting the bootstrap node on another one instead of running on
it’s own, that’ll take us down to 3 nodes.

Marco is making an OMG! charm that is a the WordPress charm but with
everything we learned today. When it’s ready the sysadmin at OMG! will
do all those commands I just showed you, and then he’ll be done, except
he’ll be running on AWS, with proper S3 integration, backup snapshots to
S3, and all the goodies and running smooth as butter.

Now that Marco is *capturing everything he’s learned* in to a charm, we
don’t have to do this by hand anymore. It will be trivial to deploy OMG.
Joey can redeploy it onto another zone for redundancy and backup, along
with all the data, probably in less than an hour, depending on how long
the data copy takes from zone to zone. In fact, I think I’m going to try
it just to see how long it takes. Things learned tonight we’ll put back
in the MySQL and WordPress charms, so that any one who wants to run
WordPress on Ubuntu can have a sweet rig.

Conclusion and Scale-o-rama
---------------------------

We showed you how deploying can become easier, and basically scripted.
That’s not even the nice part about juju. Every 6 months when Ubuntu
releases OMG!Ubuntu gets nearly overrun with traffic. One server, you
can’t scale. Unless you buy or rent another server, but he doesn’t need
another server except for those few times he’s hurtin’. Want to know how
easy it is to scale with juju? About a week before release Joey will go:

    juju add-unit wordpress-omg

And another WordPress instance will come up. Since haproxy and WordPress
already know each other it will just work. He’ll have a 2 node WordPress
instance. He can run this commands for as many nodes as he wants
depending on how much traffic is coming in. After the traffic surge is
over, he can `juju remove-unit wordpress-omg` back to one node. for
normal operations. Pay for exactly what you need and be able to grow at
a moment’s notice, that’s how we roll.

And this is just with WordPress and MySQL, a simple example, you should
see how we do Hadoop! We can do this for any [service we have a charm
for](http://charms.kapilt.com/charms). Interested in getting your stuff
on the cloud? Here’s how you can [write your own
charm](https://juju.ubuntu.com/Charms), and don’t forget to enter the
[charm
contest](http://cloud.ubuntu.com/2012/02/juju-charm-contest-help-bring-free-software-into-the-cloud/),
where we’re giving away \$500 in Amazon Gift cards for submitted charms!

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
