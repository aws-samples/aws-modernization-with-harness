---
title: "Verification Setup"
chapter: true
draft: false
weight: 16
---

# Verification Configuration 

In this step will be deploying the components necessary to collect and report on the metrics of our sample application used in this lab. The tools we'll be using include:

* [Kubernetes Metrics Server](https://docs.aws.amazon.com/eks/latest/userguide/metrics-server.html) 
* [Prometheus](https://prometheus.io) 


## Kubernetes Metrics Server
[Kubernetes Metrics Server](https://docs.aws.amazon.com/eks/latest/userguide/metrics-server.html) is an aggregator of resource usage data in your cluster, and it is not deployed by default in Amazon EKS clusters

## Prometheus
[Prometheus](https://prometheus.io) is an open-source systems monitoring and alerting toolkit. Many companies and organizations have adopted Prometheus, and the project has a very active developer and user community. It is now a standalone open source project and maintained independently of any company. Prometheus joined the Cloud Native Computing Foundation in 2016.

{{% notice note %}}
Both tools are free of cost to use, however will use resources in your clusters which in turn can have a cost.  While cost is not a factor for this AWS Workshop, please make sure to consider this when implementing these tools in your own clusters.
{{% /notice %}}