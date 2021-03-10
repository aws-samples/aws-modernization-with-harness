---
title: "4.1 Harness Setup"
chapter: true
draft: false
weight: 41
---

# Harness Setup

Once you have [signed up](http://bit.ly/harness-aws-workshop) for an account with Harness, you can log into Harness by heading to [app.harness.io](https://app.harness.io) and logging in with your credentials. Harness works on a CD Abstraction Model which will be needed to be filled out. The first step will be to install the Harness Delegate into your EKS Cluster. 

## Harness Kubernetes Delegate Install

Installing the [Harness Kubernetes Delegate](https://docs.harness.io/article/7in9z2boh6-kubernetes-quickstart) which is a worker node in your EKS Cluster is pretty straightforward. You will need kubectl access to the EKS Cluster. 

**Setup -> Harness Delegates  then Click on Install Delegate** 

* Name: “eks-delegate”

![eks-delegate](../images/install_delegate.png)

Can download to your local machine once or if using a remote machine, can copy the cURL command in the “Copy Download Link” link. 

Next will need to expand the tar.gz that was downloaded. If using a remote machine, can run
the command: 

    tar -xvf harness-delegate-kubernetes.tar.gz

Inside the expanded tar folder, there is a README.txt which has several useful commands. Run the following command against the yaml file in the folder:

    kubectl apply -f harness-delegate.yaml

After a few moments, the Delegate will be available via the Harness UI.

![delegate UI](../images/delegate_overview.png)
 
## Adding EKS Cluster to Harness
Adding the EKS Cluster to Harness is simple. To create a new [Cloud Provider](https://docs.harness.io/article/l68rujg6mp-add-kubernetes-cluster-cloud-provider) which represents the EKS Cluster, 

**Setup -> Cloud Providers + Add Cloud Provider -> Kubernetes Cluster** 

* Name: My EKS Cluster
* Cluster Details: Inherit from Selected Delegate
* Delegate: eks-delegate

![EKS Connector Setup](../images/eks_cluster_cloud_provider.png)

Once you click Next and Submit, your EKS Cluster is wired to Harness. 

## Fork and Add Workshop GitHub Repository to Harness
Fork this GitHub Repository [https://github.com/ravilach/harness-canary-workshop] into your
own account. When referring to the git configuration YAMLs, please refer to your Forked
repository. While logged into GitHub, visit https://github.com/ravilach/harness-canary-workshop
and click Fork.

![Fork Github repo](../images/fork_repo.png)

Adding your newly forked repository will allow for workshop assets to be used in Harness. 

**Setup -> Connectors -> Source Repo Providers + Add Source Repo Provider**

* Name: AWS Workshop
* URL: https://github.com/ravilach/harness-canary-workshop (your Forked address)
* Username: Your User Name
* Password/Secret: Click Pencil to add your token/pw as a Harness Secret

![Add Git Connector](../images/aws_git_connector.png)

Click Submit and the Repository is added. 

## Create a Harness Application

Harness Applications are the lifeblood of the CD Abstraction Model. The Harness Application will house everything needed to deploy. 

To create a Harness Application, 

**Setup -> Applications + Add Application** 

* Name: AWS Canary Lab

![Add Application](../images/application.png)

Once you hit Submit, a blank Application is there. 

![Application Setup](../images/application_setup.png)

## Create a Harness Environment

Harness Environments are where you are going to deploy to.

**Setup -> AWS Canary Lab -> Environments + Add Environment**

* Name: The EKS Cluster
* Type: Non-Production

![Add Environment](../images/eks_environment.png)

Once Created, define the Infrastructure Definition. You can have multiple clusters here but since the example is only using one, one will be define. 

![Add Infrastructure Definition](../images/eks_infra_def.png)

Hit Submit and now you are wired up to deploy to your EKS Cluster.  
