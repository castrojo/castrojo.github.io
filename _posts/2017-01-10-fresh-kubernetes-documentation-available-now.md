---
title: Fresh Kubernetes documentation available now
date: '2017-01-10 19:34:12'
layout: post
---
Over the past few months our team has been working real hard on the [Canonical Distribution of Kubernetes](https://www.ubuntu.com/cloud/kubernetes). This is a pure-upstream distribution of k8s with our community's operational expertise bundled in.

It means that we can use one set of operational code to get the same deployment on GCE, AWS, Azure, Joyent, OpenStack, and Bare Metal.

Like most young distributed systems, Kubernetes isn't exactly famous for it's ease of use, though there has been tremendous progress over the past 12 months. Our documentation on Kubernetes was nearly non-existent and it became obvious that we had to dive in there and bust it out. I've spent some time fixing it up and it's been recently merged. 

You can find the [Official Ubuntu Guides](http://kubernetes.io/docs/getting-started-guides/ubuntu/) in the "Create a cluster" section. We're taking what I call a "sig-cluster-lifecycle" approach to this documentation -- the pages are organized into lifecycle topics based on what an operator would do. So "Backups", or "Upgrades" instead one big page with sections. This will allow us to grow each section based on the expertise we learn on k8s for that given task. 

Over the past few months (and hopefully for Kubernetes 1.6) we will slowly be phasing out the documentation on our individual charm and layer pages to reduce duplication and move to a pure upstream workflow. 

On behalf of our team we hope you enjoy Kubernetes, and if you're running into issues please [let us know](https://github.com/juju-solutions/bundle-canonical-kubernetes/issues) or you can find us in the Kubernetes slack channels.