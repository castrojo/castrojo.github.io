---
title: 'Is a "cloud-native" home server for me? Why not?  '
layout: post
date: '2017-08-03T00:00:00-04:00'
---
I've recently embarked on a journey of trying new things in my homelab. I've been experimenting with new methods of managing my services at home, and I have tried a few combinations of methods and operating systems.  

Now that I am more familiar with the cloud native landscape, I was wondering if I could wean myself off the most stateful snowflake in my life, the trusty home server. 

I've been collecting hardware recently and decided to go out of my comfort zone and run some home services via different combinations. Let's see what I found out. 

# What do I need to run?

I have a few things I run in house that I need to host:

- A Ubiquiti Unifi controller, which controls my [network gear](https://blog.jorgecastro.org/2016/12/29/unifis-new-cheaper-switches-are-great/).
- A Ubiquiti Unifi Video controller, an entirely [different piece of software](https://www.ubnt.com/download/unifi-video/unifi-nvr) for recording video from their line of IP cameras.
- [Pi-hole](https://pi-hole.net/) for network wide privacy and ad blocking
- A [Plex Media Server](https://www.plex.tv/) for my videos.

The Unifi stuff depends on Java and MongoDB, and accesses hardware on the network. Pi-hole expects to basically be my DNS server, and Plex is the textbook definition of a stateful app; depending on the size of your video collection it can grow a substantial database that's all on disk, so moving around means bringing gigs of stuff with it.

With this varied set of apps, we shall begin!

## Old Reliable, traditional Ubuntu 16.04 with .debs

This has been working for me up to this point. As with anything involving third party packaging, this is a hot mess. 

For Unifi you need either an external Mongo repo(!) and/or a OpenJDK PPA(!) to get it to work, and even then, [ouch](https://community.ubnt.com/t5/UniFi-Video/Latest-kernel-update-for-Debian-8-9-and-Ubuntu-16-04-breaking/td-p/1968120).

Pi hole wants me to pipe a script to bash, and Plex just publishes one off debs with no repository, making that update a hassle. 

There are some benefits here, once I configure `unattended-upgrades` things generally run fine. It's a well understood system, and having the large repository of software is always good. Over time it tends to accumulate crap though. 

## Ubuntu 16.04 with Docker containers

The main advantage to this setup is I can crowdsource the maintenance of these apps to people who do a real good job, like the awesome guys at [linuxserver.io](http://tools.linuxserver.io/dockers). I can keep a _lean_ and mostly stock host, toss away broken containers if need be, and keep everything nice and isolated. 

What ppa do I need for unifi? Is my plex up to date? What java symlink do I need to fix? I don't need to care anymore! 

`docker-compose` was really good for this and relatively simple to grok, especially by stealing other people's configs from github and modifying them to my needs. 

### Why not LXD containers?

I ran with this config for a while, but it had one major issue for me. LXD containers are system containers, that is, they run a copy of the OS. So now instead of maintaining one host I am now maintaining one host OS and many client OSes. Going into each one and installing/configuring the services felt like I was adding complexity. LXD is great, just not for my specific use case.

## Ubuntu Core 16.04 with Docker containers

Finally, something totally different. I am pretty sure "home server" doesn't rank high on the use case here, but I figured I would give it a shot. I took the same `docker-compose` files from before, except this time I deploy on top of ubuntu-core. 

This gives me some nice features over the mutable-buntu. First off, atomic upgrades. Everytime it gets a new kernel it just reboots, and then on boot all the containers update and come back up.

This has a few teething issues. First off, if there's a kernel update it's just going to reboot, you can't really control that. Another is, it really is small, so it's missing tools. It can only install snaps, so no rsync, no git, no curl, no wget. I'm not going to run git out of a docker container. Also I couldn't figure out how to run docker as the non-root user and I can't seem to find the documentation on how to do that anywhere. 

## ContainerOS with Docker containers

A slim OS designed to only run containers. This one definately has a more "work related" slant to it. There's no normal installer, the installer basically takes a cloud-init-like yaml file and then dd's the disk. Or just fire up your home PXE server. :) Most of the docs don't even talk about how to configure the OS, the entire "state" is kept in this yaml file in git, it is expected that I can blow it away at any time and drop containers on it.

This comes with git, rsync, and curl/wget out of the box, so it's nice to be able to have these core tools in there instead of totally missing. There's also a 'toolbox' command that will automagically fetch a traditional distro container (defaults to fedora) and then mounts the filesystem inside, so you can 'nano' to your heart's content. 

This works really well. ContainerOS lets me dictate the update policy as part of the config file, and if I have multiple servers I can cluster them together so that they will take turns rebooting without having a service go down. But as you can see, we quickly venture out of the "home server" use case with this one. 

## ContainerOS with rkt/systemd

This is the setup I am enjoying the most. So instead of using the docker daemon, I create a systemd service file, like say '/etc/systemd/system/unifi.service'

    [Unit]
    Description=Unifi
    After=network.target
    [Service]
    Slice=machine.slice
    Type=simple
    ExecStart=/usr/bin/rkt --insecure-options=image run docker://linuxserver/unifi --volume config,kind=host,source=/home/jorge/config/unifi --mount volume=config,target=/config --net=host --dns=8.8.8.8
    KillMode=mixed
    Restart=always
    [Install]
    WantedBy=multi-user.target

Then I 'systemctl start unifi' to start it, and 'systemctl enable unifi' to enable it on boot. ContainerOS is set to reboot on Thursdays at 4am, containers update on boot. I can use 'journalctl' and 'machinectl' like I can with "normal" services. 

Note that you can use this config on any OS that has systemd and rkt. Since ContainerOS has a section in it's yaml file for writing systemd services, I can have one well maintained file that will just enable me to spit out and entire configured server in one shot. Yeah!

This one "feels" like the most future proof, as the [OCI spec](https://www.opencontainers.org/) is now finalized it feels like over time every tool will just be able to consume these images. I don't know what that means for rkt and/or docker, but you can similarly [use docker in this manner as well](http://container-solutions.com/running-docker-containers-with-systemd/).

# What about state? 

So far I've only really talked about the "installation problem", I've continually left out the hard part, the state of the applications themselves. Reinstalling coreos will get me all the apps back but no data, that doesn't sound very cloud native! 

If you look at the systemd service file above, you see I keep the state in '/home/jorge/config/plex'. I do this for each of the services. I need to find a way to make sure that that is saved somewhere else than just local disk. 

Saving this onto an NFS share earned overwhelming NOPE NOPE NOPE from the straw poll I took (and one even threatened to come over  and fight me). And that's kind of cheating by moving the problem. 

So right now this is still up in the air, I fired up a quick [duplicati](https://www.duplicati.com/) instance to keep a copy on S3. 

Really don't want to add a ceph cluster to my home administration tasks. Suggestions here would be most welcome. 

# How have they been running?

I know what you're thinking. Self rebooting servers and auto updating containers? You're high.

Surprisingly in the last three months I have been running all five of these things side by side and they've all been rock solid.

I don't know what to say here, some combination of great OS and container maintainers, or maybe not so much churn. I am going to try to keep these up and running as long as possible just to see what happens. 

# What's left to try?

The obvious hole here is the Project Atomic stack, which will be next on the list. 

And of course, it's only a matter of time until one of these reboots breaks something or a container has a bad day. 

If you think this blog post isn't crazy enough Chuck and I will be [delving into Kubernetes](https://gist.github.com/chuckbutler/92164d09fba51b2219b8bb8d4450761f) for this later on as this is all just a warm up. 