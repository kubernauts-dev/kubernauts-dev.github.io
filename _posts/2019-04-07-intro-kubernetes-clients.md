---
title: "Introduction to Kubernetes Clients"
categories:
  - Introduction
tags:
  - kubernetes
  - client
---

In Kubernauts.dev, it is assume that you know little bit about Kubernetes :) and we will discuss about Kubernetes and Developer around it :)

In this post, we will see Different Kubernetes clients, client is something which you can use to talk to kubernetes cluster.

Mainly, there are 3 ways to talk to cluster:

* [kubectl](https://kubernetes.io/docs/tasks/tools/install-kubectl/)
* [Console/Dashboard](https://kubernetes.io/docs/tasks/access-application-cluster/web-ui-dashboard/)
* programmatically using clients


kubernetes community maitains clients in various languages in this [repo](https://github.com/kubernetes-client).


Since Kubernetes is in golang, client library known as [client-go](https://github.com/kubernetes/client-go) is mostly used. But there are clients available in another interesting languages :)

* [Python](https://github.com/kubernetes-client/python)
* [Ruby](https://github.com/kubernetes-client/ruby)
* [csharp](https://github.com/kubernetes-client/csharp)
* [perl](https://github.com/kubernetes-client/perl)
* [haskell](https://github.com/kubernetes-client/haskell)
* [javascript](https://github.com/kubernetes-client/javascript)
* [java](https://github.com/kubernetes-client/java)

for java, there's one more client known as [fabric8 kubernetes client](https://github.com/fabric8io/kubernetes-client) which is also widely used  and famous too :)  (it works with OpenShift too)

In upcoming blog post, we will see how we can leverage `client-go` effectively to talk to cluster and create some tools using it.
