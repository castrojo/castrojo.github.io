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

In the cloud when you’re talking about hundreds and thousands of
instances things like logging can become a hassle. You’re certainly not
going to read every log, and you could use rsyslog. We have an [rsyslog
charm](http://jujucharms.com/charms/precise/rsyslog-forwarder) which you
can use to relate to things and send the logs to a centralized server.
But that’s still just raw logs.

There’s this *great* tool under development called
[Logstash](http://logstash.net/). It’s got a bunch of great features,
and you can just watch the author [explain it
here](http://www.youtube.com/watch?feature=player_embedded&v=RuUFnog29M4).
After seeing this video I thought, wow, this would be an awesome tool
for Ubuntu devops everywhere. So I asked if someone was interested in
working on this.

Paul Czarkowski answered the call and has submitted a set of Juju charms
for Logstash, Elastic Search, and Kibana. Here’s his [blog
post](http://tech.paulcz.net/2012/11/more-ubuntu-juju-logstash-charms.html)
on the process. You can find the three charms here:

-   <http://jujucharms.com/~paulcz/precise/elasticsearch>
-   <http://jujucharms.com/~paulcz/precise/kibana>
-   <http://jujucharms.com/~paulcz/precise/logstash-indexer>

They of course need to go through review and get into the actual store,
but I’m just excited that Paul took this one by the horns and now we
have a nice open source alternative to Splunk for users. If you’re
deploying logstash already have a look and feel free to send
improvements.

Looking to help fill out the Ubuntu logging story? Well we could
certainly use a
[Greylog2](https://bugs.launchpad.net/charms/+bug/1040175) charm to go
along with it. Inquire within!

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
