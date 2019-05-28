---
title: "Talking to the Kubernetes cluster from outside"
categories:
  - Introduction
tags:
  - Kubernetes
  - client
  - Golang
---


In a previous blog post, we have seen how we can communicate programmatically from outside of the cluster, now we will see how we can talk to API server from inside. examples for this use case are custom controllers, operators, etc


Similar to the previous function, if we don't pass either master URL or kubeconfig file path, it will fallback to `rest.InClusterConfig` (coming from `k8s.io/client-go/rest`)

```
config, err := clientcmd.BuildConfigFromFlags("", "")
```

you might be curious without providing master URL or kubeconfig file path, how it is accessing the API server, let's have a look at `inclusterConfig`

```
config, err := rest.InClusterConfig()
```

How does it work?

* first, it looks for `KUBERNETES_SERVICE_HOST` & `KUBERNETES_SERVICE_PORT` environment variables, ideally, kubernetes injects those environment variables into every pod.
* then, it  looks for `/var/run/secrets/kubernetes.io/serviceaccount/token` and `/var/run/secrets/kubernetes.io/serviceaccount/ca.crt`

with all this information, `rest.InClusterConfig` returns `rest.Config` struct which then used to create actual clientsets.

With this method, `namespace` is determined either by `POD_NAMESPACE` environment variable or by reading this file `/var/run/secrets/kubernetes.io/serviceaccount/namespace` from the pod.