---
title: "4.2 Connecting to EKS"
chapter: true
draft: false
weight: 42
---

## Adding EKS Cluster to Harness
Adding the EKS Cluster to Harness is simple. To create a new [Cloud Provider](https://docs.harness.io/article/l68rujg6mp-add-kubernetes-cluster-cloud-provider) which represents the EKS Cluster, 

**Setup -> Cloud Providers + Add Cloud Provider -> Kubernetes Cluster** 

* **Name:** ***My EKS Cluster***
* **Cluster Details:** ***Inherit from Selected Delegate***
* **Delegate:** ***eks-delegate***

![EKS Connector Setup](/images/eks_cluster_cloud_provider.png)

Once you click Next and Submit, your EKS Cluster is wired to Harness. 