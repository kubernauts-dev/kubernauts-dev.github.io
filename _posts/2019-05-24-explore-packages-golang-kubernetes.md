---
title: "Exploring packages from golang client"
categories:
  - Introduction
tags:
  - kubernetes
  - client
  - golang
---

In [last blog post](https://kubernauts.dev/introduction/2019/04/07/intro-kubernetes-clients.html), we learnt about golang kubernetes client and various ways of installing it.

There are various packages which will be used for most of the times during development.

#### Mostly used packages from `client-go`

* [`tools/clientcmd`](https://github.com/kubernetes/client-go/tree/master/tools/clientcmd) : it is used to setup client from kubeconfig file

* [`kubernetes`](https://github.com/kubernetes/client-go/tree/master/kubernetes) : it contains kubernetes API clients

with the help of those clients, we can perform actions like GET, LIST, CREATE, UPDATE, DELETE, etc operations on resources.

Along `with client-go`, there are other important repositories like:

* [`kubernetes/api`](https://github.com/kubernetes/api) which contains Go types of Kubernetes resources.

* [`kubernetes/apimachinery`](https://github.com/kubernetes/apimachinery) contains building blocks like schemes, encoding, decoding, coversion, etc.

Now we are familiar with golang client and other important repositories, let's see how we can talk to cluster using all those in next blog post.