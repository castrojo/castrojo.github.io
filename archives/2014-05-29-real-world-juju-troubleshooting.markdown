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

The following is a guest post by Ian Booth:

Juju has the ability to set up and change logging levels at a package
level so that problems within a particular area can be better diagnosed.
Recently there were some issues with containers (both kvm and lxc)
started by the local provider transitioning from pending to started. We
wanted to be able to inspect the sequence of commands Juju uses to start
a container. Fortunately, the Juju code which starts lxc and kvm
containers does log out the actual commands used to download the
requisite image and start the container et al. The logging level used
for this information is TRACE. By default, Juju machine agents log at
the debug level, and this information can be seen when running ‘juju
debug-log’. So unfortunately, this means the information we are
interested in is not visible by default in the machine logs.

Luckily we can change the logging level used for particular packages so
that the information is logged. This is done using the ‘logging-config’
attribute and can either be done at bootstrap:

    juju bootstrap --logging-config=golxc=TRACE

or on a running system:

    juju set-env logging-config=golxc=TRACE

As an aside, you can use:

    juju get-env logging-config

to see what the current logging-config value is.

The logging-config value above turns on TRACE level dubugging for the
golxc package, which is responsible for starting and managing lxc
containers on behalf of Juju. For kvm containers, the package name is
‘kvm’.

We can use debug-log to look at the logging we have just enabled. As of
1.19 onwards, filtering can be used to just show what we are interested
in. Run this command in a separate terminal:

    juju debug-log --include-module=golxc

Now we can deploy a charm or use add-machine to initiate a new
container. We can see the commands Juju issues to download the image and
start the container. This allows us to see what parameters are passed in
to the various lxc commands, and we could even manually run the commands
if we wish, in order to reproduce and examine in more detail how the
commands behave. An example of the logging information when adding TRACE
level debugging to lxc startup looks like:

    machine-0: 2014-05-27 04:28:39 TRACE golxc.run.lxc-start golxc.go:439 run: lxc-start [--daemon -n ian-local-machine-1 -c /var/lib/juju/containers/ian-local-machine-1/console.log -o
    /var/lib/juju/containers/ian-local-machine-1/container.log -l DEBUG]
    machine-0: 2014-05-27 04:28:40 TRACE golxc.run.lxc-ls golxc.go:439 run: lxc-ls [-1]
    machine-0: 2014-05-27 04:28:41 TRACE golxc.run.lxc-ls golxc.go:451 run
    successful output: ian-local-machine-1
    machine-0: 2014-05-27 04:28:41 TRACE golxc.run.lxc-info golxc.go:439 run:
    lxc-info [-n ian-local-machine-1]
    machine-0: 2014-05-27 04:28:41 TRACE golxc.run.lxc-info golxc.go:451 run
    successful output: Name: ian-local-machine-1
    machine-0: 2014-05-27 04:28:45 TRACE golxc.run.lxc-start golxc.go:448 run failed
    output: lxc-start: command get_cgroup failed to receive response
    machine-0: 2014-05-27 04:29:45 TRACE golxc.run.lxc-ls golxc.go:439 run: lxc-ls [-1]
    machine-0: 2014-05-27 04:29:45 TRACE golxc.run.lxc-ls golxc.go:451 run
    successful output: ian-local-machine-1
    machine-0: 2014-05-27 04:29:45 TRACE golxc.run.lxc-info golxc.go:439 run:
    lxc-info [-n ian-local-machine-1]
    machine-0: 2014-05-27 04:29:45 TRACE golxc.run.lxc-info golxc.go:451 run
    successful output: Name: ian-local-machine-1

You can see that when logging the various commands execute, the format
is `cmd [arg arg arg]`. So to run these manually leave out the \[\]. You
can also see that there was a problem starting the lxc container due to
a cgroups issue. This error is shown in juju status, but often it’s
useful to see what happens leading up to the error occurring.

In summary, Juju’s configurable logging output can be used to help
diagnose issues and understand what Juju is doing under the covers. It
offers the ability to turn on extra logging when required, and it can be
turned off again when no longer required.

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
