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

I was real excited to see Jeff Atwood’s
[announcement](http://www.codinghorror.com/blog/2013/02/civilized-discourse-construction-kit.html)
of [Discourse](http://www.discourse.org). It’s about time someone
rebooted forum software.

Since it’s an Open Source project I was immediately keen on seeing how
we could help. One of the more interesting discussions is [the choice of
platform](http://meta.discourse.org/t/technology-stack-choices/1457). I
find this discussion interesting because in the age of devops some
people consider Rails and Postgres to be “weird”. Nevermind that we
finally have a bold project to fix the status quo of terrible
discussions on the internet, let’s argue about languages and databases.
But I digress.

Our job with Ubuntu Server is to make it easy for you to deploy stuff. I
honestly don’t really care what language or technology you use, if you
use Ubuntu as your deployment platform I want to help you, period. So,
an exciting new project that people want to play with? After seeing
people contributing on [getting it to
work](http://meta.discourse.org/t/anyone-got-this-running-on-heroku-yet/625/24)
on Heroku I figured we could easily get this up and charmed. Let’s get
to work.

Marco’s finished the charm, it took him about 2 days of on-and-off. You
can find it here.

-   <http://jujucharms.com/~marcoceppi/precise/discourse>

This will deploy the latest Discourse and Postgres to your cloud (Tested
on EC2 for now, more to come) and you have your test forum.

![](http://www.jorgecastro.org/images/discourse.png)

When you run `upgrade-charm` it’ll just fetch the latest source,
db:migrate, re-compile assets, then restart the application, so you get
nice fresh Discourse right from trunk, which at this point in it’s life
is useful. There’s still many things we’ll need to sort, like adding
other units and distilling more expertise from the Discourse community
as it becomes available. You can try Discourse on the
[try.discourse.org](http://try.discourse.org) sandbox, and discuss the
project itself on [meta](http://meta.discourse.org). The thread for the
charm is
[here](http://meta.discourse.org/t/deploying-discourse-to-amazon-and-other-clouds/1632).

Here’s a quick list of things we need help on:

-   an upstart script (would be a great contribution to upstream)
-   Testing it on HP Cloud and OpenStack

We also need help keeping track with upstream, like you’d expect this
team moves *fast*, and getting this up and running so early is bound to
have bumps, so anyone willing to help us add features to the charm so
that people can help testing would be appreciated. Fasten your
seatbelts, the 1990’s are not going to go away quietly!

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
