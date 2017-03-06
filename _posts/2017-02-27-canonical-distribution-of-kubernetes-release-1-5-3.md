---
title: Canonical Distribution of Kubernetes - Release 1.5.3
date: '2017-02-27 08:30:08'
layout: post
---

We’re proud to announce support for Kubernetes 1.5.3 in the Canonical Distribution of Kubernetes. This is a pure upstream distribution of Kubernetes, designed to be easily deployable to public clouds, on-premise (ie vsphere, openstack), bare metal, and developer laptops. Kubernetes 1.5.2 is a patch release comprised of mostly bugfixes, and we encourage you to [check out the release notes](https://github.com/kubernetes/kubernetes/blob/master/CHANGELOG.md/#changelog-since-v152).

## Getting Started:

Here’s the simplest way to get a Kubernetes 1.5.3 cluster up and running on an Ubuntu 16.04 system:

```
sudo snap install conjure-up --classic
conjure-up kubernetes
```

During the installation conjure-up will ask you what cloud you want to deploy on and prompt you for the proper credentials. If you’re deploying to local containers (LXD) see [these instructions](https://kubernetes.io/docs/getting-started-guides/ubuntu/local/) for localhost-specific considerations.

For production grade deployments and cluster lifecycle management it is recommended to read the [full Canonical Distribution of Kubernetes documentation](https://kubernetes.io/docs/getting-started-guides/ubuntu/).

Home page: [https://jujucharms.com/canonical-kubernetes/](https://jujucharms.com/canonical-kubernetes/)

Source code: [https://github.com/juju-solutions/bundle-canonical-kubernetes](https://github.com/juju-solutions/bundle-canonical-kubernetes)

## How to upgrade

With your kubernetes model selected, you can deploy the bundle to upgrade your cluster if on the 1.5.x series of kubernetes. At this time releases before 1.5.x have not been tested. Depending on which bundle you have previously deployed, run:

```
    juju deploy canonical-kubernetes
```

or

```
    juju deploy kubernetes-core
```

If you have made tweaks to your deployment bundle, such as deploying additional worker nodes as a different label, you will need to manually upgrade the components. The following command list assumes you have made no tweaks, but can be modified to work for your deployment.

```
juju upgrade-charm kubernetes-master
juju upgrade-charm kubernetes-worker
juju upgrade-charm etcd
juju upgrade-charm flannel
juju upgrade-charm easyrsa
juju upgrade-charm kubeapi-load-balancer
```

This will upgrade the charm code, and the resources to kubernetes 1.5.3 release of the Canonical Distribution of Kubernetes.

## New features:

- Full support for Kubernetes v1.5.3.
- K8s master charm now properly keeps distributed master files in sync for an HA control plane.

## General Fixes

- [#41251](https://github.com/kubernetes/kubernetes/pull/41251) - Fix UpdateAddonsTactic to use local repo
- [#42058](https://github.com/kubernetes/kubernetes/pull/42058) - Fix shebangs in charm actions to use python3
- [#41815](https://github.com/kubernetes/kubernetes/pull/41815) - enable DefaultTolerationSeconds admission controller by default
- [#41351](https://github.com/kubernetes/kubernetes/pull/41351) - Multi master patch 
- [#41256](https://github.com/kubernetes/kubernetes/pull/41256) - Lint fixes for the master and worker Python code
- [#41919](https://github.com/kubernetes/kubernetes/pull/41919) - Juju: Disable anonymous auth on kubelet  (Thanks to community member @raesene for pointing this out!)

## etcd Specific Fixes

- [#74](https://github.com/juju-solutions/layer-etcd/pull/74) - Add the ability to attach NRPE to etcd for monitoring with an external Nagios server.
- [#76](https://github.com/juju-solutions/layer-etcd/pull/76) - Add the debug action to the etcd charm that makes it easier to collect debug information in the field.

## Test Results

The Canonical Distribution of Kubernetes is a running daily tests to verify it works with the upstream code. As part of the Kubernetes test infrastructructure we upload daily test runs. The test results are available on the dashboard. Follow along with our progress here:

- [https://k8s-gubernator.appspot.com/builds/canonical-kubernetes-tests/logs/kubernetes-gce-e2e-node/](https://k8s-gubernator.appspot.com/builds/canonical-kubernetes-tests/logs/kubernetes-gce-e2e-node/)

## How to contact us:

We're normally found in these Slack channels and attend these sig meetings regularly:

- [sig-cluster-lifecycle](https://kubernetes.slack.com/messages/sig-cluster-lifecycle/)
- [sig-cluster-ops](https://kubernetes.slack.com/messages/sig-cluster-ops/)

Operators are an important part of Kubernetes, we encourage you to participate with other members of the Kubernetes community!

We also monitor the Kubernetes mailing lists and other [community channels](http://kubernetes.io/community/), feel free to reach out to us. As always, PRs, recommendations, and bug reports are welcome: [https://github.com/juju-solutions/bundle-canonical-kubernetes](https://github.com/juju-solutions/bundle-canonical-kubernetes)
