---
title: "7.1 Metrics Server Install"
chapter: true
draft: false
weight: 51
---


## Kubernetes Metrics Server
Installing the Metrics Server can be done in one kubectl command. 

    kubectl apply -f https://github.com/kubernetes-sigs/metrics-server/releases/latest/download/components.yaml

![kubctl apply metrics server](/images/install_metrics_server.png)