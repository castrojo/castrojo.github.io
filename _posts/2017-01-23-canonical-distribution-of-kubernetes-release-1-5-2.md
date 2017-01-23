---
title: Canonical Distribution of Kubernetes - Release 1.5.2
date: '2017-01-23 08:30:08'
layout: post
---
We’re proud to announce support for Kubernetes 1.5.2 in the Canonical Distribution of Kubernetes. This is a pure upstream distribution of Kubernetes, designed to be easily deployable to public clouds, on-premise (ie vsphere, openstack), bare metal, and developer laptops. Kubernetes 1.5.2 is a patch release comprised of mostly bugfixes, and we encourage you to [check out the release notes](https://github.com/kubernetes/kubernetes/blob/master/CHANGELOG.md#changelog-since-v151).

## Getting Started:

Here’s the simplest way to get a Kubernetes 1.5.2 cluster up and running on an Ubuntu 16.04 system:

```
sudo apt-add-repository ppa:juju/stable
sudo apt-add-repository ppa:conjure-up/next
sudo apt update
sudo apt install conjure-up
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

This will upgrade the charm code, and the resources to kubernetes 1.5.2 release of the Canonical Distribution of Kubernetes.

## New features:

* Full support for Kubernetes v1.5.2.

## General Fixes

* [#151](https://github.com/juju-solutions/bundle-canonical-kubernetes/issues/151) [#187](https://docs.google.com/document/d/1amyUwQSrDrSc28FZFFqW0rWnKUcm7nYax6_TXBAyirw/edit#) It wasn’t very transparent to users that they should be using conjure-up when locally developing, conjure-up is now the defacto default mechanism for deploying CDK.

* [#173](https://github.com/juju-solutions/bundle-canonical-kubernetes/issues/173) Resolved permissions on ~/.kube on kubernetes-worker units

* [#169](https://github.com/juju-solutions/bundle-canonical-kubernetes/issues/169) Tuned the verbosity of the AddonTacticManager class during charm layer build process

* [#162](https://github.com/juju-solutions/bundle-canonical-kubernetes/issues/162) Added NO_PROXY configuration to prevent routing all requests through configured proxy [by [@axinojolais](https://github.com/axinojolais)]

* [#160](https://github.com/juju-solutions/bundle-canonical-kubernetes/issues/160) Resolved an error by flannel sometimes encountered during cni-relation-changed [by [@spikebike](https://github.com/spikebike)]

* [#172](https://github.com/juju-solutions/bundle-canonical-kubernetes/issues/172) Resolved sporadic timeout issues between worker and apiserver due to nginx connection buffering [by [@axinojolais](https://github.com/axinojolais)]

* [#101](https://github.com/juju-solutions/kubernetes/pull/101) Work-around for offline installs attempting to contact pypi to install docker-compose

* [#95 ](https://github.com/juju-solutions/kubernetes/pull/95)Tuned verbosity of copy operations in the debug script for debugging the debug script.

## Etcd layer-specific changes

* [#72](https://github.com/juju-solutions/layer-etcd/issues/72) [#70](https://github.com/juju-solutions/layer-etcd/issues/70) Resolved a certificate-relation error where etcdctl would attempt to contact the cluster master before services were ready [by [@javacruft](https://github.com/javacruft)]

## Unfiled/un-scheduled fixes:

* [#190](https://github.com/juju-solutions/bundle-canonical-kubernetes/issues/190) Removal of assembled bundles from the repository. See bundle author/contributors notice below

## Additional Feature(s):

* We’ve open sourced our release management process scripts we’re using in a juju deployed jenkins model. These scripts contain the logic we’ve been running by hand, and give users a clear view into how we build, package, test, and release the CDK. You can see these scripts in the [juju-solutions/kubernetes-jenkins](https://github.com/juju-solutions/kubernetes-jenkins) repository. This is early work, and will continue to be iterated on / documented as we push towards the Kubernetes 1.6 release.

## Notice to bundle authors and contributors:

The fix for [#190](https://github.com/juju-solutions/bundle-canonical-kubernetes/issues/190) is a larger change that has landed in the [bundle-canonical-kubernetes](https://github.com/juju-solutions/bundle-canonical-kubernetes) repository. Instead of maintaining several copies across several repositories of a single use-case bundle; we are now assembling the CDK based bundles as fragments (un-official nomenclature).

This affords us the freedom to rapidly iterate on a CDK based bundle and include partner technologies, such as different SDN vendors, Storage backend components, and other integration points. Keeping our CDK bundle succinct, and allowing the more complex solutions to be assembled easily, reliably, and repeatedly. This does change the contribution guidelines for end users.

Any changes to the core bundle should be placed in its respective fragment under the [fragments](https://github.com/juju-solutions/bundle-canonical-kubernetes/tree/master/fragments) directory. Once this has been placed/merged, the primary published bundles can be assembled by running `./bundle` in the root of the repository. This process has been outlined in the repository [README.md](https://github.com/juju-solutions/bundle-canonical-kubernetes#bundle-builder-for-cdk)

We look forward to any feedback on how opaque/transparent this process is, and if it has any useful applications outside of our own release management process. The `./bundle` python script is still very much geared towards our own release process, and how to assemble bundles targeted for the CDK. However we’re open to generalizing them and encourage feedback/contributions to make this more useful to more people.

## How to contact us:

We're normally found in these Slack channels and attend these sig meetings regularly:

* [sig-cluster-lifecycle](https://kubernetes.slack.com/messages/sig-cluster-lifecycle/)

* [sig-cluster-ops](https://kubernetes.slack.com/messages/sig-cluster-ops/)

Operators are an important part of Kubernetes, we encourage you to participate with other members of the Kubernetes community!

We also monitor the Kubernetes mailing lists and other [community channels](http://kubernetes.io/community/), feel free to reach out to us. As always, PRs, recommendations, and bug reports are welcome: [https://github.com/juju-solutions/bundle-canonical-kubernetes](https://github.com/juju-solutions/bundle-canonical-kubernetes)
