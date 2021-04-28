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

Confirm the metrics server has started and is running successfully.

    watch kubectl get pods -n kube-system -l k8s-app=metrics-server

![kubectl get pods](/images/kubectl_metrics_server.png)

Once the pod is running, type **CTRL-C** to exit
