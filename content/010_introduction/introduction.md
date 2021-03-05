# Your First Automated Canary Deployment in EKS

Welcome to your first automated canary deployment in EKS/Kubernetes. 
By leveraging the [Harness](https://harness.io/platform/).

## Moving Pieces

There will be a few moving pieces. 

* An Amazon EKS Cluster with the ability to deploy
* A Harness Account in which you [can sign up here](http://bit.ly/harness-aws-workshop)

## Description

During the deployment, will be deploying a stable then unstable version of the [Harness Sample Application](https://hub.docker.com/r/harness/cv-demo)
to show the virtues of an automated canary deployment. 

Prometheus will be used to automate the canary deployment as the primary source of metric verification. The lab will walk through installing and configuring Prometheus.
