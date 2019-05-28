---
title: "Introduction to Kubernetes Clients"
categories:
  - Introduction
tags:
  - Kubernetes
  - client
---

In Kubernauts.dev, it is assumed that you know a little bit about Kubernetes and we will discuss Kubernetes and Developer around it.

In this post, we will see Different Kubernetes clients, the client is something which you can use to talk to kubernetes cluster.

Mainly, there are 3 ways to talk to cluster:

* [kubectl](https://kubernetes.io/docs/tasks/tools/install-kubectl/)
* [Console/Dashboard](https://kubernetes.io/docs/tasks/access-application-cluster/web-ui-dashboard/)
* programmatically using clients


the kubernetes community maintains clients in various languages in this [repo](https://github.com/kubernetes-client).


Since Kubernetes is in Golang, client library known as [client-go](https://github.com/kubernetes/client-go) is mostly used. But there are clients available in other interesting languages :)

* [Python](https://github.com/kubernetes-client/python)
* [Ruby](https://github.com/kubernetes-client/ruby)
* [C Sharp](https://github.com/kubernetes-client/csharp)
* [Perl](https://github.com/kubernetes-client/perl)
* [Haskell](https://github.com/kubernetes-client/haskell)
* [Javascript](https://github.com/kubernetes-client/javascript)
* [Java](https://github.com/kubernetes-client/java)

for Java, there's one more client known as [fabric8 kubernetes client](https://github.com/fabric8io/kubernetes-client) which is also widely used  and famous too :)  (it works with OpenShift too)

In the upcoming blog post, we will see how we can leverage `client-go` effectively to talk to cluster and create some tools using it.
