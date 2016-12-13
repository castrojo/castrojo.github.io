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

Attaching a number or value to something that you can sort-of measure
can lead to a bunch of problems. But if you’re like me you like to see
some sort of quantitative way to measure something. I mean, that’s what
science is all about, right? If something is better than something else,
you should be able to measure that.

Unfortunately, the world doesn’t entirely work this way, how else can
you explain anomalies like [this album winning a
Grammy](http://en.wikipedia.org/wiki/St._Anger)? Well, you really can’t.
At the end of the day there’s some subjective measure *somewhere* about
something.

It can be this way with software. While you can measure things like
performance, stability, uptime, and so on, this kind of measurement is
specific. It’s specific to a service, a deployment, based on certain
hardware, and so on. And we knew we needed to measure the quality and
“awesomeness” of things in the Juju Charm Store. After all, if you want
to deploy something in the cloud you at least want to know how well it
works. We handle a bunch of the quality for you; we do reviews, we run
tests, and the “science” that when you run something it will reasonably
work. What we don’t really handle right now is the opinionated “and it
does all these right things too”. One of the original “you’re doing it
right” things people know about is the [Joel
Test](http://www.joelonsoftware.com/articles/fog0000000043.html).

![](http://www.jorgecastro.org/images/joeltest.jpg){.middle}

These aren’t very scientific, they’re just simple questions. Some don’t
even make sense in some fields. No, my company doesn’t use the best
tools money can buy, because the best tools in our space are Free
Software. But either way, generally speaking, you can look at that list
and then look at a place where you’re applying for a job and make a
reasonable assessment if that place is right for you. It can certainly
help you avoid the bottom of the barrel. Of course you’ll still find
many discussions about which of these questions is appropriate,
inappropriate, what’s missing, and so on, but, as a quick and dirty view
on something, the Joel Test works well enough.

So over the past week [we
proposed](https://lists.ubuntu.com/archives/juju/2012-September/001853.html)
an idea similar to Joel’s Test but for Juju Charms in Ubuntu. This
criteria is more of a [list of general
practices](https://juju.ubuntu.com/CharmGuide) that you’d want to strive
for. However many of those criteria your charm meets gives you a rough
general idea on how mature a charm is.

Things like reliability, security, flexibility, handling data,
scalability, and so on. While we can measure many of these things with
science (For example, if your charm doesn’t pass `charm proof` then
that’s an easy measurement), some of these things are more subjective
and more generally described. We’d love to see every charm [handle data
in version control](http://jujucharms.com/charms/precise/wordpress) like
the wordpress charm, so we made that one of the things we look for. We
leave it up to the author to determine the best way to handle that user
data, but generally it’s an area we want.

Just like I don’t need to read every review of Skyrim, just tell me if
it’s a decent enough game and I’ll play it:

![](http://www.jorgecastro.org/images/skyrim.jpg){.middle}

So while these categories are really general and we could easily argue
over scales, points, and other minutia, what we’re really looking to
accomplish here is a way to see where a charm stands in relation to
where we want to be. So how do our charms do with this new criteria?
Pretty terrible. The ideal charm doesn’t exist, and there’s things that
we added to the criteria that we know will be hard work to strive to,
but it’s a good watermark to see how far we need to go to give people
something that they’d run in their own environments.

And then of course, since the Charm Store doesn’t freeze like say, the
release of a video game, the onus is on us to provide the community with
resources on how to improve their charms to improve their score over
time, but that’s a topic for another day!

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
