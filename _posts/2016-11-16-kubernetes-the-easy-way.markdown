---
layout: post
title: "Kubernetes the Easy Way"
date: 2016-11-16 10:00
comments: true
categories: [kubernetes, juju]
---

If you're interested in running Kubernetes you've probably heard of Kelsey Hightower's [Kubernetes the Hard Way](https://github.com/kelseyhightower/kubernetes-the-hard-way). Exercises like these are important, they highlight the coordination needed between components in modern stacks, and it highlights how far the world has come when it comes to software automation. Could you imagine if you had to set everything up the hard way every time?

## Learning is fun

Doing things the hard way is fun, once. After that, I've got work to do, and soon after I am looking around to see who else has worked on this problem and how I can best leverage the best open source has to offer.

It reminds me of the 1990's when I was learning Linux. Sure, as a professional, you need to know systems and how they work, down to the kernel level if need. Having to do those things without a working keyboard or network makes that process much harder. Give me a working computer, and then I can begin. There's value in learning how the components work together and understanding the architecture of Kubernetes, I encourage everyone to try the hard way at least one time, if anything it'll make you appreciate the work people are putting into automating all of this for you in a composable and reusable way.

## The easy way

I am starting a new series of videos on how we're making the Canonical Distribution of Kubernetes easy for anyone to deploy on any cloud. All our code is [open source](https://github.com/juju-solutions/bundle-canonical-kubernetes) and we love pull requests. Our goal is to help people get Kubernetes in as many places as quickly and easily as possible. We've incorporated lots of the things people tell us they're looking for in a production-grade Kubernetes, and we're always looking to codify those best practices. 

Enjoy:  

<iframe width="560" height="315" src="https://www.youtube.com/embed/B7nMFVaOOi8" frameborder="0" allowfullscreen></iframe>

Following these steps will get you a working cluster, in this example I'm deploying to `us-east-2`, the shiny new AWS region. Subsequent videos will cover how to interact with the cluster and do more things with it. 