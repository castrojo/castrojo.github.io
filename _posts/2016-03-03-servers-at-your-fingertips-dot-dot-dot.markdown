---
layout: post
title: "Servers at your fingertips..."
date: 2016-03-03 16:02
comments: true
categories: [ubuntu, lxc]
---

One of the nice things about system containers is that it makes the cost of creating a new machine essentially zero. With [LXD 2.0](https://linuxcontainers.org/lxd/news/) around the corner this is now easier than ever. LXD now ships with native simplestreams support, which means we can now list and cache all sorts of interesting OS cloud images.

You can see every image provided by doing a `lxc image list images:`, but the nice thing is the syntax is easy to remember. You can now just launch all sorts of Linux Server cloud images from all sorts of vendors and projects:  

    $ lxc launch images:centos/7/amd64 test-centos
    Creating test-centos
    Retrieving image: 100%
    Starting test-centos
    $ lxc exec test-centos /bin/bash
    [root@test-centos ~]# yum update
    Loaded plugins: fastestmirror

... and so on. Give em a try:

    lxc launch images:debian/sid/amd64
	lxc launch images:gentoo/current/amd64
	lxc launch images:oracle/6.5/i386
	
And of course ubuntu is supported:

    lxc launch ubuntu:14.04

So if you're sick of manually snagging ISOs for things and keeping those up to date, then you'll dig 16.04, just install LXD and you can launch any Linux almost instantly. We'll keep 'em cached and updated for you too. I can `lxc launch ubuntu:12.04` and do `python --version` faster than I can look it up on packages.ubuntu.com. That's pretty slick. 
