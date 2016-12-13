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

**Call for Help and Ideas!**

Everyone knows I [love web
apps](http://castrojo.tumblr.com/post/815726909/web-apps-interact-with-me).
You have two extremes. Old school “native apps and in control of my
data” and then the other which is basically ChromeOS; No local state,
all web. Most people are in the middle. You might love Gmail but the
thought of having a remote word processor might not work for you.

I want my cake and I want to eat it too. I want web apps integrated with
my desktop, which is why I am a big fan of [site specific
browsers](http://en.wikipedia.org/wiki/Site-specific_browser). Recently
these have been popularized by Chrome applications in the Chrome App
Store – which is just a pretty front-end to what Stuart and I have been
yelling about for 3 years.

When people do it right  (like [Seesmic](http://seesmic.com/app) and
[Tweetdeck](http://www.tweetdeck.com/chrome/)), it’s a great user
experience. When people do it wrong, it’s just a stupid bookmark with no
window chrome, meh. However, we can do little things to make it great. 

One area where we can integrate is notifications. Chrome/Webkit has
notifications, they look like this: 

![](http://media.tumblr.com/tumblr_lemflqIBzZ1qb5bmy.png)

These are becoming more popular; Seesmic, Stack Overflow Chat, and
irccloud to name a few. Well, why stop there? I asked Aq to hook up a
prototype and then [Marco Cepppi](http://twitter.com/#!/marcoceppi)
finished it.

Let’s *chromify-osd*:

![](http://media.tumblr.com/tumblr_lemj9nXuKx1qb5bmy.png)

A little bit of glue makes all the difference. To try it:

> bzr branch lp:chromify-osd

> cd chromify-osd

> python chrome\_notifyosd\_server.py

Now, load the extension in Chrome. Wrench -&gt; Tools -&gt; Extensions,
click on the developer mode link, and then choose Load unpacked
extension and select the directory “chromify-osd”. Then use a webapp
that uses extensions. Here’s [an example
one](http://www.phpguru.org/html5-webkit-desktop-notifications-example).

Aq passes along “Although remember that the best solution will still be
to write a **proper** Chrome extension which intercepts notifications
and uses D-Bus! An NPAPI extension. This is a *hack*.”

So what do we need? We need someone who can make a Chromium extension to
connect web notifications to libnotify. I suspect that a proper
extension will have to deal with sandboxing and a bunch of stuff Aq
glazed over in order to give me hope that this is possible.

What else do we need? Well, we need Unity to decide to be the glue for
the web. We can do this by connecting desktop services to the browsers.
Wherever web app developers take this we need to connect it up for
people. [Here is the
start](https://wiki.ubuntu.com/UnityWebIntegrationPlan) of some plans
Unity developers have for making this integration better.

Any takers on getting this started?

Where else can we do this? How about we make it so when people make the
App Shortcut we “install it” for them?

![](http://media.tumblr.com/tumblr_lemfw5irmq1qb5bmy.png)

Now we’re talking! I also what a nice high resolution icon on the
launcher with little numbers for new emails, etc. fta pointed [out the
code](http://src.chromium.org/svn/trunk/src/chrome/browser/shell_integration_linux.cc) where
Chromium does the shortcut thing, maybe someone can take a crack at it
once the Launcher gets closer to being finished.

(My examples use Chrome since it ships app shortcuts out of the box, the
same should apply for Firefox/Prism)

Whether you agree with web apps or not isn’t the point. Some people like
them and some people don’t, either way your desktop should give you the
best possible experience if you use Evolution or Gmail or whatever.
Thoughts?

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
