---
title: "AWS Cleanup"
chapter: true
draft: false
weight: 91
---

## Delete an EKS Cluster
Here is how to delete the EKS Cluster you've provisioned:

1. Go to your [Cloud9 IDE](https://us-east-1.console.aws.amazon.com/cloud9/home?region=us-east-1)
1. In the command line, check out all the namespaces that are attached to your EKS cluster:
   ```sh
    kubectl get svc --all-namespaces
   ```
1. Delete any services that has an associated **EXTERNAL-IP value**
   ```sh
    # These services are fronted by an ELB which must be deleted for associated resources to be released properly
    kubectl delete svc <service-name>
   ```
1. Delete the EKS cluster with the code snippet below:
    ```sh
    # If you named your EKS cluster something other than basic-eks, replace the basic-eks below with the name used
    eksctl delete cluster --name basic-eks
    ```
1. This process may take up to 30 minutes for everything to be fully deleted.

## Delete Cloud9 Instance
Now that we've deleted the EKS cluster, we can now safely delete our Cloud9 EC2 instance:

1. Go to your [EC2 dashbord](https://console.aws.amazon.com/ec2/v2/home?region=us-east-1#Instances:) 
1. Select the EC2 instance with the name "harness-workshop"
1. Go to the actions drop down menu and select delete instance