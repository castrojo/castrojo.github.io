---
layout: post
title: "New wiki bundles for you to play with..."
date: 2016-04-05 12:19
comments: true
categories: juju, ubuntu
---

I've pushed new sample bundles to the [Juju Charm Store](http://jujucharms.com). The first is a simple mediawiki with mysql:

<script async src="https://assets.ubuntu.com/v1/juju-cards-v1.2.0.js"></script>

<div class="juju-card" style="width:600px" data-id="bundle/wiki-simple-0"></div>

For a more scalable approach I've also pushed up a version with MariaDB, haproxy, and memcached. This allows you to add more wiki units to horizontally scale:

<div class="juju-card" style="width:600px" data-id="~jorge/bundle/wiki-scalable-0"></div>

I'll be working on a "smoosh everything onto one machine" bundle next, so stay tuned!
