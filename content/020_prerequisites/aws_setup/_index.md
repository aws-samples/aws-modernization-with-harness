---
title: "AWS Setup"
chapter: true
draft: false
weight: 10
---

# Workshop Prerequisites
<a href={{< ref "24_aws_event_setup.md" >}}><img src="/images/ee_logo.png"></a>

There are a few prerequisite tasks you must perform before getting started on this workshop. These are:

1. Access an AWS account
2. Launch Cloud9 IDE Workspace
3. Sign-up for a [Harness Trial account](http://bit.ly/exclusive-trial)
4. An Amazon EKS Cluster with the ability to deploy

We will step through each of these in turn.

{{% notice info %}}
If you are attending an AWS-hosted workshop, the account you're using will have an EKS Cluster pre-provisioned with a m5.large node, an ELB, and all IAM roles already created.
{{% /notice %}}

{{% notice warning %}}
If you are NOT attending an AWS-hosted workshop, you will need to provision your own EKS Cluster. Please follow this [link](https://docs.aws.amazon.com/eks/latest/userguide/eksctl.html) on how to create your own EKS Cluster via eksctl.
{{% /notice %}}

