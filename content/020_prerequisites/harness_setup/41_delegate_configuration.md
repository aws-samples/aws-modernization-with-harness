---
title: "4.1 Delegate Configuration"
chapter: true
draft: false
weight: 41
---

## Harness Kubernetes Delegate Install

{{% notice note %}} 
The Harness Delegate is a scalable worker node that can be deployed as a linux process on an EC2 instance, an ECS task, or to k8s via a manifest or helm chart.  For this lab we will be using a k8s manifest.  This is the only Harness software that needs to be installed by the customer.  All other Harness services are provided by Harness as a SaaS provider. 
{{% /notice %}}

Installing the [Harness Kubernetes Delegate](https://docs.harness.io/article/7in9z2boh6-kubernetes-quickstart) which is a worker node in your EKS Cluster is pretty straightforward. You will need kubectl access to the EKS Cluster and should be able to connect using your Cloud9 Console. 

Log into your Harness environment with your browser at the following URL:  https://app.harness.io


**Setup -> Harness Delegates  then Click on Install Delegate** 

* **Download Type:** ***"Kubernetes YAML"***
* **Name:** ***“eks-delegate”***

![Harness Delegate Setup](/images/harness_delegate_eks.gif)

Can download to your local machine once or if using a remote machine, can copy the cURL command in the “Copy Download Link” link. 

Next will need to expand the tar.gz that was downloaded. If using a remote machine, can run
the command: 

    tar -xvf harness-delegate-kubernetes.tar.gz

Inside the expanded tar folder, there is a README.txt which has several useful commands. Run the following commands against the yaml file in the folder:
    
    sed -i 's/memory: "8Gi"/memory: "2Gi"/g' harness-delegate.yaml

    sed -i 's/cpu: "1"/cpu: ".25"/g' harness-delegate.yaml

{{% notice note %}}
The Harness Delegate is sized for production use cases, the above commands are to set it to minimum requirements for the workshop
{{% /notice %}}

    kubectl apply -f harness-delegate.yaml

After a few moments, the Delegate will be available via the Harness UI.

{{% notice note %}}
The Implicit Selectors in the image below are automatically provided based on the deployment of the Delegate and can be used for [scoping of the Delegate](https://docs.harness.io/article/hw56f9nz7q-scope-delegates-to-harness-components-and-commands) to specific resources, applications, clusters, etc..  Additionally one can add Custom Selectors for the same purpose.
{{% /notice %}}

![delegate UI](/images/delegate_overview.png)
 
