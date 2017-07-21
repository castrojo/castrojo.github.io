---
title: TLDRing your way to a Kubernetes Bare Metal cluster
layout: post
date: '2017-07-21T11:00:50+00:00'
---
Alex Ellis has an [excellent tutorial](https://blog.alexellis.io/kubernetes-in-10-minutes/) on how to install Kubernetes in 10 minutes. It is a summarized version of what you can find in the [official documentation](https://kubernetes.io/docs/setup/independent/install-kubeadm/). Read those first, this is a an even shorter version with my choices mixed in. 

We'll install 16.04 on some machines, I'm using three. I just chose to use Weave instead of sending you to a choose your-own-network page as you have other stuff to learn before you dive into an opinion on a networking overlay. We're also in a lab environment so we assume some things like your machines are on the same network. 

### Prep the Operating System

First let's take care of the OS. I set up automatic updates, ensure the latest kernel is installed, and then ensure we're all up to date, whatever works for you: 
    
    sudo -s
    dpkg-reconfigure unattended-upgrades
    apt install linux-generic-hwe-16.04
    apt update
    apt dist-upgrade
    reboot

### Prep each node for Kubernetes: 

This is just installing docker and adding the kubernetes repo, we'll be root for these steps: 

    sudo -s
    curl -s https://packages.cloud.google.com/apt/doc/apt-key.gpg | apt-key add -
    cat <<EOF >/etc/apt/sources.list.d/kubernetes.list
    deb http://apt.kubernetes.io/ kubernetes-xenial main  
    EOF
    
    apt update
    apt install -qy docker.io kubelet kubeadm kubernetes-cni

### On the master:

Pick a machine to be a master, then on that one: 

    kubeadm init

And then follow the directions to copy your config file to your user account, we only have a few commands left needed with sudo so you can safely `exit` out and continue with your user account: 

    mkdir -p $HOME/.kube
    sudo cp -i /etc/kubernetes/admin.conf $HOME/.kube/config
    sudo chown $(id -u):$(id -g) $HOME/.kube/config
    
Let's install the network, and then allow workloads to be scheduled on the master (for a lab we want to use all our hardware for workloads!): 

    kubectl apply -f https://git.io/weave-kube-1.6
    kubectl taint nodes --all node-role.kubernetes.io/master-

### On each worker node: 

On each machine you want to be a worker (yours will be different, the output of `kubeadm init` will tell you what to do: 

    sudo kubeadm join --token 030b75.21ca2b9818ca75ef 192.168.1.202:6443 

You might need to tack on a `--skip-preflight-checks`, see [#347](https://github.com/kubernetes/kubeadm/issues/347), sorry for the inconvenience.


## Ensuring your cluster works

It shouldn't take long for the nodes to come online, just check em out: 

    $ kubectl get nodes
    NAME       STATUS     AGE       VERSION
    dahl       Ready      45m       v1.7.1
    hyperion   NotReady   16s       v1.7.1
    tediore    Ready      32m       v1.7.1

    $ kubectl cluster-info
    Kubernetes master is running at https://192.168.1.202:6443
    KubeDNS is running at https://192.168.1.202:6443/api/v1/namespaces/kube-system/services/kube-dns/proxy

    To further debug and diagnose cluster problems, use 'kubectl cluster-info dump'
    $
    
 Ok you're cluster is rocking, now
 
 ## Set up your laptop
 
 I don't like to be ssh'ed into my cluster unless I'm doing maintenance, so now that we know stuff is working let's copy the kubernetes config from the master node to our local workstation. You should know how to copy files around systems already, but here's mine for reference: 
 
     sudo scp /etc/kubernetes/admin.conf jorge@ivory.local:/home/jorge/.kube/config
     
  I don't need the entire Kubernetes repo on my laptop, so we'll just install the snap for kubectl and check that I can access the server: 
       
      sudo snap install kubectl --classic
      kubectl get nodes
      kubectl cluster-info
      
   ## Deploy your first application
   
   Let's deploy the Kubernetes dashboard: 
   
       kubectl create -f https://git.io/kube-dashboard
       kubectl proxy
      
   Then hit up [http://localhost:8001/ui](http://localhost:8001/ui).
   
   That's it, enjoy your new cluster! 