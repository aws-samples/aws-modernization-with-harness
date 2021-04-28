---
title: "6.3 Create Harness Environment"
chapter: true
draft: false
weight: 40
---

## Create a Harness Environment

Harness Environments are where you are going to deploy to.

**Setup -> AWS Canary Lab -> Environments + Add Environment**

* **Name:** ***The EKS Cluster***
* **Type:** ***Non-Production***

![Add Environment](/images/eks_environment.png)

Click **Submit**.  Once Created, select **Add Infrastructure Definition** to define an infrastructure definition for this environment. You can add multiple infrastructure definitiions but since the example is only using one, one will be all that is needed. 

![Add Infrastructure Definition](/images/eks_infra_def.png)

Click **Submit** and now you are wired up to deploy to your EKS Cluster.  
