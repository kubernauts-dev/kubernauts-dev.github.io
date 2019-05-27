---
title: "Talking to kubernetes cluster from outside"
categories:
  - Introduction
tags:
  - kubernetes
  - client
  - golang
---


With reference to previous blog post, we are importing `clientcmd` package to work on kubeconfig which contains essential information like cluster URL, namespace,auth details to talk to cluster.

```
import k8s.io/client-go/tools/clientcmd
```

[`BuildConfigFromFlags`](https://github.com/kubernetes/client-go/blob/master/tools/clientcmd/client_config.go#L539) function from `clientcmd` creates config from either master URL or kubeconfig filepath.

```
config, err := clientcmd.BuildConfigFromFlags("", kubeconfigPath)
```
 
if nothing (master URL or kubeconfig filepath) is provided, then it will fallback to `inClusterConfig` which we will see in next blog post.

if `err` is occured that means, kubeconfig is not parsed properly or `kubeconfigPath` is not correct.

`config` is of type [`rest.Config`](https://github.com/kubernetes/client-go/blob/master/rest/config.go#L52) (coming from [`k8s.io/client-go/rest`](https://github.com/kubernetes/client-go/rest)) which then used to create actual clientsets. we will see that in upcoming blogposts.


if you just want to play around kubeconfig, you can also use,

```
config, err := clientcmd.LoadFromFile(kubeConfigPath)
```

where `config` is of type [`clientcmdapi.Config`](https://github.com/kubernetes/client-go/blob/master/tools/clientcmd/api/types.go#L31) which is go struct for kubeconfig.

sample kubeconfig:

```
apiVersion: v1
clusters:
- cluster:
    certificate-authority-data: REDACTED
    server: https://192.168.42.120:8443
  name: 192-168-42-120:8443
contexts:
- context:
    cluster: 192-168-42-120:8443
    namespace: myproject
    user: developer/192-168-42-120:8443
  name: minishift
current-context: minishift
kind: Config
preferences: {}
users:
- name: developer/192-168-42-120:8443
  user:
    token: <token>
```