---
layout: post
title: "Kubernetes v1.3.3 for Ubuntu ready for testing"
date: 2016-07-29 10:28
comments: true
categories: kubernetes, juju
---

We've been trailing the [Kubernetes 1.3](http://blog.kubernetes.io/2016/07/kubernetes-1.3-bridging-cloud-native-and-enterprise-workloads.html) release for the past few weeks, mostly to ensure that etcd data migrations are preserved from 1.2 to 1.3. We're also in the process of adding TLS between all the nodes for security reasons, and that has led to use being a bit behind on getting Kubernetes 1.3 out to you, but don't worry, we're in the process of testing the upgrade path and this post will outline how to set up a Kubernetes 1.2 cluster and upgrade it to v1.3.3. Once we get good feedback from the community on how this is working out for you, we'll go ahead and set v1.3.3 (or subsequent version) as the new default for Ubuntu Kubernetes.

 Our bundle, which we call "observable-kubernetes" features the following model:

- Kubernetes (automating deployment, operations, and scaling containers)
  - Three node Kubernetes cluster with one master and two worker nodes.
  - TLS used for communication between nodes for security.
- Etcd (distributed key value store)
  - Three node cluster for reliability.
- Elastic stack
   - Two nodes for ElasticSearch
   - One node for a Kibana dashboard
   - Beats on every Kubernetes and Etcd node:
     - Filebeat for forwarding logs to ElasticSearch
     - Topbeat for inserting server monitoring data to ElasticSearch

As usual, you get pure Kubernetes direct from upstream and of course it's cross-cloud, making it easy for you to use your own bare metal for deployment. 

## Your First Kubernetes Cluster

After [configuring Juju](https://jujucharms.com/docs/stable/getting-started) to use the cloud you prefer we can start the cluster deployment.

    juju deploy observable-kubernetes

This will deploy the bundle with default constraints. This is great for testing out Kubernets but most clouds won't give you enough CPU and memory to use the cluster in anger, so I recommend [checking out the documentation](https://github.com/juju-solutions/bundle-observable-kubernetes) on how to modify the bundle to more accurately reflect either the hardware you have on hand, or the instance size you prefer.

We can watch the cluster coming up with a `watch juju status`, this will give us a near-realtime view of the cluster as it comes up:

![kubes](/images/kubes.png)

## Making sure your cluster works 

We just wait for things to come up and hit an idle state before moving on. Once we're up we can manage the cluster with `kubectl`. We've provided this tool for you on the master node with a config file prepoluated for you, first let's find the master node.

    juju run --application kubernetes is-leader

The output will show you which node is the master node, you can then copy the tools to your local machine:

    juju scp kubernetes/0:kubectl_package.tar.gz .

Untar that wherever you'd like and cd to that directory, you should have a kubectl binary and a `kubeconfig` file for you to use along with `kubectl`. You can now check the status of your cluster with:

    ./kubectl cluster-info --kubeconfig ./kubeconfig 
    Kubernetes master is running at https://104.196.123.155:6443
    KubeDNS is running at https://104.196.123.155:6443/api/v1/proxy/namespaces/kube-system/services/kube-dns

Now let's check the version of Kubernetes we're running, note how it responds with both the client and server version.

    ./kubectl version --kubeconfig ./kubeconfig 
    Client Version: version.Info{Major:"1", Minor:"2", GitVersion:"v1.2.3", GitCommit:"882d296a99218da8f6b2a340eb0e81c69e66ecc7", GitTreeState:"clean"}
    Server Version: version.Info{Major:"1", Minor:"2", GitVersion:"v1.2.3", GitCommit:"882d296a99218da8f6b2a340eb0e81c69e66ecc7", GitTreeState:"clean"}

## Upgrading to a new version 

So far we've done the usual bits on getting Kubernetes running on Ubuntu, now we're ready to test the latest stuff from upstream. 

    juju set-config kubernetes version=v1.3.1

And then check `juju status` again while the model mutates. Now let's see the version:

    ./kubectl version --kubeconfig ./kubeconfig 
    Client Version: version.Info{Major:"1", Minor:"2", GitVersion:"v1.2.3", GitCommit:"882d296a99218da8f6b2a340eb0e81c69e66ecc7", GitTreeState:"clean"}
    Server Version: version.Info{Major:"1", Minor:"3", GitVersion:"v1.3.1", GitCommit:"fe4aa01af2e1ce3d464e11bc465237e38dbcff27", GitTreeState:"clean"}

Aha! As you see here, the cluster has upgraded to v1.3.1, but my local tools are obviously still v1.2.3. Obviously I can just recopy the kubectl tarball from the master node again, but I appear to have made a mistake, as the latest upstream version of Kubernetes is actually v1.3.3. No worries man:

        juju set-config kubernetes version=v1.3.3

And let's check our version:

    ./kubectl version --kubeconfig ./kubeconfig
    Client Version: version.Info{Major:"1", Minor:"2", GitVersion:"v1.2.3", GitCommit:"882d296a99218da8f6b2a340eb0e81c69e66ecc7", GitTreeState:"clean"}
    Server Version: version.Info{Major:"1", Minor:"3", GitVersion:"v1.3.3", GitCommit:"c6411395e09da356c608896d3d9725acab821418", GitTreeState:"clean"}

Now that my cluster is up to date, don't forget to copy a new version of `kubectl` from the master so that your client is also up to date. Now we're ballin' and on the latest upstream, now we can go ahead and [dive into the Kubernetes docs](http://kubernetes.io/docs/hellonode/) to get started deploying a real workload inside your cluster. 

## Future Goals

So why isn't v1.3.3 the default? Well we'd like to see some real feedback from people first and we're still in the process of validating that your data will get migrated without issues as you upgrade. As you can see upgrading an empty cluster is trivial, and we'd like to make sure we've dotted all the t's and i's before moving on. 

We'd also like to take the next few weeks to prep the charms for the upcoming v1.4 release, as well as revving the etcd and Elastic stacks to their latest upstream versions, as well as revving the OS itself to xenial so that the ZFS backed storage is more robust and has a better out-of-the-box experience. We should also make it so that getting `kubectl` from the master isn't so annoying. 

Got any feedback for us? You can find us on the [Juju mailing list](https://lists.ubuntu.com/mailman/listinfo/juju) and #sig-cluster-ops and #sig-cluster-lifecycle on [kubernetes.slack.com](kubernetes.slack.com). Hope to see you there!






    
