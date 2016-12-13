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

I wonder why people ask for advice in [all the wrong
places](http://linux.slashdot.org/article.pl?sid=09/03/09/236230). Let
me save this guy some time, and anyone else who may be asking, because
this can get complicated and people are always giving out wrong advice.

**Jorge’s Guide to Deploying Awesome Linux Desktops**

Stupid Things People Need to Learn:

-   The terms “LDAP” and “Active Directory” are not interchangeable.

-   When someone asks about Group Policy Objects stop saying “puppet”
    or “cfengine”. First off, puppet is only part of the solution, stop
    ignoring the rest of the problem! And why are people still
    recommending cfengine? Stop!

-   “Don’t give your users root access” isn’t enough. It’s not just
    about installing software.

-   I know what LTSP is, answer the original question!

-   NFS home directories and LDAP logins is NOT ACTIVE DIRECTORY.

Things No One Will Tell You:

-   What you want to do will probably be complicated. Cross-platform
    desktops with single sign on and policies is not trivial.

-   FIND someone who has done this before and ASK them questions.

-   At some point someone on your team will start to say things like
    this(At this point, run away): “oh this is easy, we’ll just run this
    perl script I found on the internet on every desktop, then use rsync
    to deploy this and then mount this over NFS, then we’ll invoke it
    all in their .bashrc, then we’ll create this account on every box …
    oh, don’t forget about making that dummy LDAP account because I
    can’t figure out anonymous binds, oh and this account needs to be
    UID 0 to get this to work (better prefix it with a capital R), and
    then all we have to do is run “make” every time we add a user! oh no
    wait… one sec, let me check the source code…”

-   I have not investigated likewise-open but it’s probably a good idea
    to look into it, certainly before you get to the step above.

-   I’ve not had to do this in like a year and a half, but I’m willing
    to bet it hasn’t gotten any better. Those of you in the audience
    paying attention will note that even though I have done this I
    haven’t documented any of it either. That’s because I’m lazy!

-   If you need to integrate Windows then your solution will probably
    require an Active Directory. No, Samba4 isn’t ready for this yet. I
    want it too, but such is life.

Don’t let it get you down though, when done right a nice integrated
desktop is possible and is a sweet, sweet thing. One thing is for sure,
the initial setup is difficult, and there are a lack of tools there (You
can however set up a pretty automated PXE setup that hands off to puppet
for example), but none of these things come out of the box and you’re
going to have to mess with them to make them work just the way you want
them to. Certainly the Ubuntu [Server
Team](https://wiki.ubuntu.com/ServerTeam) has been making great strides
in this area. LDAP server out-of-the-box! There was a time when such a
thing seemed impossible!

People are going to argue that this kind of thing is what makes Linux so
great, and some will argue that this sort of thing is what is holding
Linux back, but if it wasn’t this people would be arguing about
notification bubbles, emacs/vi, or whatever. *shrug*

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
