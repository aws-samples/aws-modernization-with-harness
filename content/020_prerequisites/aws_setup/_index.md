---
title: "AWS Setup"
chapter: true
draft: false
weight: 10
---

# Workshop Prerequisites

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

Here's a flow chart to illustrate the 2 flows:
{{<mermaid align="left">}}
graph LR;
A[Modernization Workshop *You are here!*]
A --> B[AWS Hosted Event Setup]
A --> C[On-Your-Own Event Setup]
B --> D[Create Cloud9 Instance/Roles etc.]
C --> D
{{< /mermaid >}}

## Access an AWS account
To start the workshop, follow one of the following depending on whether you are...

* [Attending an AWS hosted event](/20_prerequisites/12_aws_event_setup.html), or
* [Running the workshop on your own](/20_prerequisites/14_aws_setup_your_own.html)

Once you have completed with either setup, continue with [**Launch a Cloud9 IDE Workspace**](/20_prerequisites/16_start_cloud9workspace.html)

In this section, we'll cover the following topics:

{{% children showhidden="false" %}}