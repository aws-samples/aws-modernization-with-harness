---
title: "4.1 Delegate Configuration"
chapter: true
draft: false
weight: 41
---

## Harness Kubernetes Delegate Install

Installing the [Harness Kubernetes Delegate](https://docs.harness.io/article/7in9z2boh6-kubernetes-quickstart) which is a worker node in your EKS Cluster is pretty straightforward. You will need kubectl access to the EKS Cluster. 

**Setup -> Harness Delegates  then Click on Install Delegate** 

* Name: “eks-delegate”

![eks-delegate](/images/install_delegate.png)

Can download to your local machine once or if using a remote machine, can copy the cURL command in the “Copy Download Link” link. 

Next will need to expand the tar.gz that was downloaded. If using a remote machine, can run
the command: 

    tar -xvf harness-delegate-kubernetes.tar.gz

Inside the expanded tar folder, there is a README.txt which has several useful commands. Run the following command against the yaml file in the folder:

    kubectl apply -f harness-delegate.yaml

After a few moments, the Delegate will be available via the Harness UI.

![delegate UI](/images/delegate_overview.png)
 
