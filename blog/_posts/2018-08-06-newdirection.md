---
layout: post
title:  "An Exciting New Direction"
date:   2018-08-06 17:15:31 +0200
author: The Kubic Team
---
Dear Community,

It's been over a year since we started the Kubic project, and it's worth looking back over the last months and evaluating where we've suceeded, where we haven't, and sharing with you all our plans for the future.

# A stable base for the future

Much of our success has been in the area generally referred to as **MicroOS**, the part of the Kubic stack which provides a stable operating system that is **atomicly updated** for running containers. Not only is Kubic MicroOS now a fully integrated part of the openSUSE Tumbleweed release process, but our [Transactional Update stack has also been ported to regular openSUSE Tumbleweed and Leap]({{ site.baseurl }}{% post_url 2018-04-04-transactionalupdates %}).  
Based on your feedback the new System Role [has been further refined]({{ site.baseurl }}{% post_url 2018-04-20-transactionalupdates2 %}) and now includes fully automated updates out of the box.  
This collaboration is continuing, with many minor changes to the regular openSUSE installation process coming soon based on lessons learned with tuning the installation process in Kubic.

# Reviewing our initial premise

We haven't just been busy on the basesystem. Our efforts with [Rootless Containers](https://rootlesscontaine.rs) continue, and you can now use the "Docker-alternative" [Podman]({{ site.baseurl }}{% post_url 2018-03-25-podman %}) in both Kubic and regular openSUSE. But when considering the [Initial Premise]({{ site.baseurl }}{% post_url 2018-03-22-introduction %}) of the Kubic project, it's probably safe to say we're not where we hoped to be by now.

When we started in May 2017, our friends at SUSE were already well underway developing their first version of SUSE CaaS Platform. Alongside the general goal of making Kubic the easiest-to-live-with community Kubernetes distribution, a big part of the intial premise was to establish itself as a 'close upstream' community for SUSE CaaS Platform. In order set things up in a way similar to that you see between openSUSE Tumbleweed and SUSE Linux Enterprise), the plan was to rebase the SUSE CaaS Stack, including the Velum cluster bootstrapping tool onto the shared Kubic/Tumbleweed codebase. After a year, this goal has still proven elusive.  
This is for a number of reasons, including the wonderfully fast pace of change of Tumbleweed and aspects of the initial design of SUSE CaaS Platform which was conceptualised for the needs of SUSE's commercial customers, with the needs of developing within Kubic being an afterthought.
Obviously, this status quo has been tricky for all of us involved in Kubic, with the collective feeling being a desire to simultaniously close the gap between the Kubic and SUSE CaaS codebases, while also keeping up with the ever evolving container landscape, especially surrounding Kubernetes.

# The world has shifted

Mentioning Kubernetes, it's worth considering just how much has changed with kubernetes upstream in the 2 years since SUSE CaaS Platform development began. Back then there was no common tool for setting up and configuring a Kubernetes cluster. This was one of the primary motiviators for creating `Velum`, a key part of the SUSE CaaS Stack. However these days there are multiple tools, including the increasingly pervasive [kubeadm](https://kubernetes.io/docs/setup/independent/install-kubeadm/) which is used both standalone and as an integrated part of many larger solutions.  
A number of Kubic community members are already actively working on kubeadm, and it is increasingly interesting to the SUSE CaaS developers as a potentially key part of future SUSE CaaS Platform versions.
Kubeadm has proven itself as an increasingly mature, and flexible platform for setting up a Kubernetes cluster. There are lots of exciting features already baked into kubeadm, and we can really see it's potential for making setting up Kubic Kubernetes clusters quickly and easily, fitting in with our general goal of having Kubic as the easiest-to-live-with community Kubernetes distribution.  
Talking about it among the team, we're universally excited by this idea of adopting kubeadm as a key part of Kubic, and we're keen to focus our energies in this direction, which means changes for the Kubic you know today.

# Changes inbound!

What does this mean for Kubic users and contributors? 

 * We're going to stop our efforts to syncronise the existing SUSE CaaS Stack on Kubic. The existing **Admin, Worker, and Unconfigured** system roles will be removed soon.
 * We're going to focus on getting **kubeadm** fully working as a first-class solution on Kubic. You can expect to see new installation options and documentation in this direction **soon**.
 * The SUSE CaaS Platform team are fully on board with this idea and will be more actively contributing to Kubic, investigating the potential use of **kubeadm** for future CaaS Platform versions

As you can probably imagine, these changes are likely to be quite major, so please mind any dust or disruption as we refocus Kubic in this new direction. We intend to keep this blog updated to share our progress, but most importantly **this is not something we wish to do alone.**

We think this new direction is **really exciting** and we want more contributors to help get involved.

# How can I help?

One of the easiest ways to get involved is contributing directly to [kubeadm upstream](https://github.com/kubernetes/kubeadm). We have no desire of maintaining lots of Kubic specific patches, we plan to do as much of our work upstream first as possible, so any work you do there on behalf of Kubic will greatly help everyone.

When it comes to condensing that upstream code into an integrated product, we're going to continue using the [openSUSE Build Service](https://build.opensuse.org) as our platform of choice for building packages, container, and VM images.  
Contributing to Kubic will stay much the same, following the regular [openSUSE Factory Process](https://en.opensuse.org/openSUSE:How_to_contribute_to_Factory).  
You can expect to see some packages moving from the existing `devel:CaaSP` Devel Project to our new Devel Project `devel:kubic`. This is so we can move those packages in `devel:kubic` at full speed, while `devel:CaaSP` can remain focused on the needs of SUSE CaaS Platform.  
There will soon also be `devel:kubic:containers` and `devel:kubic:images` subprojects where we'll be baking the new Container and VM images respectively as we figure out what we need there.  
This new approach brings with it the added benefit of giving us more freedom than previously to experiment in new directions and add new packages and version as we the community see fit, without needing to worry so much about the impact on our downstream partners.

So if you have any ideas, or just need help to get started contributing, please **get in touch with us!**

You can reach us on our new mailinglist - [mailto:opensuse-kubic@opensuse.org](opensuse-kubic@opensuse.org)  
To subscribe just email [mailto:opensuse-kubic+subscribe@opensuse.org](opensuse-kubic+subscribe@opensuse.org)  
Or if you prefer IRC chat, you can find us in **#kubic** on irc.freenode.org

We are currently using this [Trello board](https://trello.com/b/wjHyQDK6/kubic-project) to track and organise our work.  
Everyone can see what we're working on, and for the moment if you'd like to join the board, please reach out for access as a contributor.

We're really excited to be taking Kubic in this new direction and hope the wider community reading this support us in this new direction and help contribute to making Kubic into the coolest, most practical, and most open community Kubernetes platform.

Thanks, and Have a lot of fun!

<img src="{{ "/assets/images/logo.svg" | prepend: site.baseurl }}" style="width:200px;" class="">
