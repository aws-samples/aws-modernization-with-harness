---
title: "5. Create an EKS Cluster"
chapter: true
weight: 16
---

## Create an EKS Cluster

Amazon EKS, also known as [Elastic Kubernetes Service](https://aws.amazon.com/eks/) is AWS' managed Kubernetes service. Provisioning an EKS Cluster is very simple and can be done with 2 steps: installing [eksctl](https://docs.aws.amazon.com/eks/latest/userguide/getting-started-eksctl.html) and using eksctl to create the cluster! eksctl is command line utility created for managing Kubernetes clusters on Amazon EKS.

### Installing eksctl
```sh
# Download and extract eksctl for Linux environment
curl --silent --location "https://github.com/weaveworks/eksctl/releases/latest/download/eksctl_$(uname -s)_amd64.tar.gz" | tar xz -C /tmp

# Move eksctl binary to /usr/local/bin
sudo mv /tmp/eksctl /usr/local/bin

# Test that eksctl has been installed in your Cloud9 instance
eksctl version
```

### Creating EKS Cluster
```sh
# Creating an EKS cluster via eksctl
eksctl create cluster \
--name basic-eks \
--region us-east-1\
--zones us-east-1a,us-east1b
```

{{% notice tip %}}
This step will take roughly 30 minutes to complete. What's happening under the hood is eksctl is provisioning an EKS cluster via CloudFormation. You can go to the CloudFormation dashboard to see what it's doing!
{{% /notice %}}

You can also go to the EKS dashboard to see if your cluster has finished provisioning. Once your cluster is created, please go to the next page and configure your Cloud9 workspace!