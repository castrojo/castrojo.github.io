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

Hey! The [Rails charm](http://jujucharms.com/charms/precise/rails) made
it into the Juju Charm Store today. It’s ready for wider community
consumption… and contributions, of course! Deploying Rails in the past
consisted of sticking configuration files for tools such as Capistrano
directly into your application’s repository. Well… we don’t really have
to do that anymore.

Here’s how it works… assuming your Rails app is “myapp”, let’s deploy
your application with mysql to show you the kind of workflow we’re
aiming to provide. Assuming you have a myapp.yaml file describing your
application:

    myapp:
      app_name: myapp
      repo_type: git
      repo_url: "https://github.com/mmm/testrails.git"

Now you’re to deploy on your cloud provider, this can be AWS, HP Cloud,
your own OpenStack, or your local Ubuntu laptop:

    juju bootstrap  
    juju deploy --config ~/myapp.yaml rails myapp
    juju deploy mysql

relate them

    juju add-relation mysql myapp

open it up to the outside world

    juju expose myapp

Find the myapp instance’s public URL from

    juju status

Like all services that can connect to a reverse proxy, Mark’s made it so
that you can easily scale out your application horizontally via haproxy:

    juju deploy haproxy
    juju add-relation haproxy myapp
    juju add-unit -n5 myapp
    juju expose haproxy  # Change your DNS to point to this IP instead
    juju unexpose myapp  # We’re behind haproxy now, no need to leave this open to the world. 

And that’s it!

What about Rails and gem versioning? One of the first things Rails
developers tell us is that Rails and Ruby packages in distros are too
static and out of date to meet their rapidly evolving needs. So how do
we handle this in the charm? Well, ironically, the Rails charm doesn’t
even install Rails. What it does is install rvm, then bundle installs
from the Gemfile in your app. This really provides the most flexibility
for your app.

Just some notes from Mark that would make this charm more compelling:

-   Stronger integration with tools like capistrano - perhaps a
    “jujustrano” gem that would allow developers to `cap manage` juju
    services if possible. This would provide continuity for your current
    devops workflow, remember that the backends can be your local
    laptop, a public cloud, or a private cloud, the steps are *all the
    same*.
-   Postgresql relations: We love to see charms that let people use
    whatever database they prefer to use.
-   Memcached relations: This is a real low hanging fruit, we could make
    it easier to just add a memcached relation to your application and
    have that just work.
-   Mongodb relations: This would be slick, our Mongo charm is pretty
    rocking, giving people an integration point with Rails would be a
    welcome contribution.
-   Ability to deploy a generic rack-based app (Sinatra)… perhaps this
    is another charm?
-   Ability to swap out Apache Passenger with Unicorn or maybe even
    Mongrel? Mark was more familiar with Passenger since those are the
    applications his company was shipping so that’s what he wrote in
    the charm. However one of the beauties of Juju is that you can write
    hooks for whatever service you need to use:

This could look something like

    juju set rails webserver=unicorn  # just an example
    juju set rails webserver=nginx    # or whichever webserver you prefer. 

Looking for more? Check out the charm at:

-   <http://github.com/charms/rails>
-   <http://jujucharms.com/charms/precise/rails>

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
