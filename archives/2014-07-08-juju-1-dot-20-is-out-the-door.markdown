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

The following is a guest post from Curtis Hovey, the Juju release
manager. You can find the original announcement on the [Juju mailing
list](https://lists.ubuntu.com/archives/juju/2014-July/003995.html).

A new stable release of Juju, juju-core 1.20.0, is now available.

Getting Juju
------------

juju-core 1.20.0 is available for utopic and backported to earlier
series in the following PPA:

-   <https://launchpad.net/~juju/+archive/stable>

New and Notable
---------------

-   High Availability
-   Availability Zone Placement
-   Azure Availability Sets
-   Juju debug-log Command Supports Filtering and Works with LXC
-   Constraints Support instance-type
-   The lxc-use-clone Option Makes LXC Faster for Non-Local Providers
-   Support for Multiple NICs with the Same MAC
-   MAAS Network Constraints and Deploy Argument
-   MAAS Provider Supports Placement and add-machine
-   Server-Side API Versioning

High Availability
-----------------

The juju state-server (bootstrap node) can be placed into high
availability mode. Juju will automatically recover when one or more the
state-servers fail. You can use the ‘ensure-availability’ command to
create the additional state-servers:

    juju ensure-availability

The ‘ensure-availability’ command creates 3 state servers by default,
but you may use the ‘-n’ option to specify a larger number. The number
of state servers must be odd. The command supports the ‘series’ and
‘constraints’ options like the ‘bootstrap’ command. You can learn more
details by running ‘juju ensure-availability –help’

Availability Zone Placement
---------------------------

Juju supports explicit placement of machines to availability zones
(AZs), and implicitly spreads units across the available zones.

When bootstrapping or adding a machine, you can specify the availability
zone explicitly as a placement directive. e.g.

    juju bootstrap --to zone=us-east-1b
    juju add-machine zone=us-east-1c

If you don’t specify a zone explicitly, Juju will automatically and
uniformly distribute units across the available zones within the region.
Assuming the charm and the charm’s service are well written, you can
rest assured that IaaS downtime will not affect your application.
Commands you already use will ensure your services are always available.
e.g.

    juju deploy -n 10 <service>

When adding machines without an AZ explicitly specified, or when adding
units to a service, the ec2 and openstack providers will now
automatically spread instances across all available AZs in the region.
The spread is based on density of instance “distribution groups”.

State servers compose a distribution group: when running ‘juju
ensure-availability’, state servers will be spread across AZs. Each
deployed service (e.g. mysql, redis, whatever) composes a separate
distribution group; the AZ spread of one service does not affect the AZ
spread of another service.

Amazon’s EC2 and OpenStack Havana-based clouds and newer are supported.
This includes HP Cloud. Older versions of OpenStack are not supported.

Azure availability sets
-----------------------

Azure environments can be configured to use availability sets. This
feature ensures services are distributed for high availability; as long
as at least two units are deployed, Azure guarantees 99.95% availability
of the service overall. Exposed ports will be automatically load
balanced across all units within the service.

New Azure environments will have support for availability sets by
default. To revert to the previous behaviour, the
‘availability-sets-enabled’ option must be set in environments.yaml like
so:

    availability-sets-enabled: false

Placement is disabled when ‘availability-sets-enabled’ is true. The
option cannot be disabled after the environment is bootstrapped.

Juju debug-log Command Supports Filtering and Works with LXC
------------------------------------------------------------

The ‘debug-log’ command shows the consolidate logs of all juju agents
running on all machines in the environment. The command operates like
‘tail -f’ to stream the logs to the your terminal. The feature now
support local-provider LXC environments. Several options are available
to select which log lines to display.

The ‘lines’ and ‘limit’ options allow you to select the starting log
line and how many additional lines to display. The default behaviour is
to show the last 10 lines of the log. The ‘lines’ option selects the
starting line from the end of the log. The ‘limit’ option restricts the
number of lines to show. For example, you can see just 20 lines from
last 100 lines of the log like this:

    juju debug-log --lines 100 --limit 20

There are many ways to filter the juju log to see just the pertinent
information. A juju log line is written in this format:

    <entity> <timestamp> <log-level> <module>:<line-no> <message>

The ‘include’ and ‘exclude’ options select the entity that logged the
message. An entity is a juju machine or unit agent. The entity names are
similar to the names shown by ‘juju status’. You can exclude all the log
messages from the bootstrap machine that hosts the state-server like
this:

    juju debug-log --exclude machine-0

The options can be used multiple times to select the log messages. This
example selects all the message from a unit and its machine as reported
by status:

    juju debug-log --include unit-mysql-0 --include machine-1

The ‘level’ option restricts messages to the specified log-level or
greater. The levels from lowest to highest are TRACE, DEBUG, INFO,
WARNING, and ERROR. The WARNING and ERROR messages from the log can seen
thusly:

    juju debug-log --level WARNING

The ‘include-module’ and ‘exclude-module’ are used to select the kind of
message displayed. The module name is dotted. You can specify all or
some of a module name to include or exclude messages from the log. This
example progressively excludes more content from the logs

    juju debug-log --exclude-module juju.state.apiserver
    juju debug-log --exclude-module juju.state
    juju debug-log --exclude-module juju

The ‘include-module’ and ‘exclude-module’ options can be used multiple
times to select the modules you are interested in. For example, you can
see the juju.cmd and juju.worker messages like this:

    juju debug-log --include-module juju.cmd --include-module juju.worker

The ‘debug-log’ command output can be piped to grep to filter the
message like this:

    juju debug-log --lines 500 | grep amd64

You can learn more by running ‘juju debug-log –help’ and ‘juju help
logging’

Constraints Support instance-type
---------------------------------

You can specify ‘instance-type’ with the ‘constraints’ option to select
a specific image defined by the cloud provider. The ‘instance-type’
constraint can be used with Azure, EC2, HP Cloud, and all
OpenStack-based clouds. For example, when creating an EC2 environment,
you can specify ‘m1.small’:

    juju bootstrap --constraints instance-type=m1.small

Constraints are validated by all providers to ensure values conflicts
and unsupported options are rejected. Previously, juju would reconcile
such problems and select an image, possibly one that didn’t meet the
needs of the service.

The lxc-use-clone Option Makes LXC Faster for Non-Local Providers
-----------------------------------------------------------------

When ‘lxc-use-clone’ is set to true, the LXC provisioner will be
configured to use cloning regardless of provider type. This option
cannot be changed once it is set. You can set the option to true in
environments.yaml like this:

    lxc-use-clone: true

This speeds up LXC provisioning when using placement with any provider.
For example, deploying mysql to a new LXC container on machine 0 will
start faster:

    juju deploy --to lxc:0 mysql

Support for Multiple NICs with the Same MAC
-------------------------------------------

Juju now supports multiple physical and virtual network interfaces with
the same MAC address on the same machine. Juju takes care of this
automatically, there is nothing you need to do.

Caution, network settings are not upgraded from 1.18.x to 1.20.x. If you
used juju 1.18.x to deploy an environment with specified networks, you
must redeploy your environment instead of upgrading to 1.20.0.

The output of ‘juju status’ will include information about networks when
there is more than one. The networks will be presented in this manner:

    machines: ...
    services: ...
    networks:
      net1:
        provider-id: foo
        cidr: 0.1.2.0/24
        vlan-tag: 42

MaaS Network Constraints and Deploy Argument
--------------------------------------------

You can specify which networks to include or exclude as a constraint to
the deploy command. The constraint is used to select a machine to deploy
the service’s units too. The value of ‘networks’ is a comma-delimited
list of juju network names (provided by MaaS). Excluded networks are
prefixed with a “\^”. For example, this command specify the service
requires the “logging” and “storage” networks and conflicts with the
“db” and “dmz” networks.

    juju deploy mongodb --constraints networks=logging,storage,^db,^dmz

The network constraint does not enable the network for the service. It
only defines what machine to pick.

Use the ‘deploy’ command’s ‘networks’ option to specify service-specific
network requirements. The ‘networks’ option takes a comma-delimited list
of juju-specific network names. Juju will enable the networks on the
machines that host service units.

Juju networking support is still experimental and under development,
currently only supported with the MaaS provider.

    juju deploy mongodb --networks=logging,storage

The ‘exclude-network’ option was removed from the deploy command as it
is superseded by the constraint option.

There are plans to add support for network constraint and argument with
Amazon EC2, Azure, and OpenStack Havana-based clouds like HP Cloud in
the future.

MAAS Provider Supports Placement and add-machine
------------------------------------------------

You can specify which MAAS host to place the juju state-server on with
the ‘to’ option. To bootstrap on a host named ‘fnord’, run this:

    juju bootstrap --to fnord

The MAAS provider support the add-machine command now. You can provision
an existing host in the MAAS-based Juju environment. For example, you
can add running machine named fnord like this:

    juju add-machine fnord

Server Side API Versioning
--------------------------

The Juju API server now has support for a Version field in requests that
are made. For this release, there are no RPC calls that require anything
other than ‘version=0’ which is the default when no Version is supplied.
This should have limited impact on existing CLI or API users, since it
allows us to maintain exact compatibility with existing requests. New
features and APIs should be exposed under versioned requests.

For details on the internals (for people writing API clients), see [this
document](https://docs.google.com/document/d/1fPOSUu7Dc_23pil1HGNTSpdFRhkMHGxe4o6jBghZZ1A/edit?usp=sharing).

Finally
-------

We encourage everyone to subscribe the mailing list at juju-dev at
lists.canonical.com, or join us on \#juju-dev on freenode.

PS. Juju just got 20% more amazing.

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
