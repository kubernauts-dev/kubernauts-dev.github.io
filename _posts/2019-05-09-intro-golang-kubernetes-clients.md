---
title: "Introduction to Golang Kubernetes Client"
categories:
  - Introduction
tags:
  - Kubernetes
  - client
---

In [last blog post](https://kubernauts.dev/introduction/2019/04/07/intro-kubernetes-clients.html), we learnt about different clients which can be used to talk to kubernetes cluster.


In this post, we will see Golang Kubernetes client, which is also known as `client-go`.

* source code for `client-go` can be found here: `https://github.com/kubernetes/client-go`

Check [Installation guide](https://github.com/kubernetes/client-go/blob/master/INSTALL.md) to install `client-go` using various methods:

* [Glide](https://github.com/kubernetes/client-go/blob/master/INSTALL.md#glide)
* [Godep](https://github.com/kubernetes/client-go/blob/master/INSTALL.md#godep)
* [Go modules](https://github.com/kubernetes/client-go/blob/master/INSTALL.md#go-modules)

If you want to try out or write simple scripts, you can use the following and get `client-go` from master
(Stability not guaranteed)

```
go get k8s.io/client-go
```

Note: `k8s.io/..` is just an alias to `github.com/kubernetes/..`, no need to confuse :D


In the upcoming blog post, we will see how we can use `client-go` effectively to talk to cluster and create some tools using it.
