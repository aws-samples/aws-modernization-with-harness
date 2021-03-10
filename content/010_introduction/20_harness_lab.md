---
title: "Harness Canary EKS Lab"
chapter: true
draft: false
weight: 20
---

# Your First Automated Canary Deployment in EKS

Welcome to your first automated canary deployment in EKS/Kubernetes by leveraging the [Harness Platform](https://harness.io/platform/).  During the deployment, you will be deploying a stable then unstable version of the [Sample Application](https://hub.docker.com/r/harness/cv-demo) to demonstrate the virtues of an automated canary deployment.

Prometheus will be used to automate as the primary source of metric verification for the canary deployment. The lab will walk through installing and configuring Prometheus as well as configuring the Harness pipeline to validate a good deployment.

## Why a Canary Deployment in EKS?:

A major drawback to a canary deployment is how complex it can be because manual verification or testing can take time and the required monitoring may involve additional research. With Harness canary deployments become just as easy to implement as a traditional rolling deployment. Developers can now choose this release strategy that is the lowest risk-prone and cheapest.

Harness and AWS are presenting a DevDay event to demonstrate how easy it is to quickly and reliably create a canary deployment. In the next 2.5 hours, you will follow our instructor and use your Harness and AWS accounts to dive into the features of Harness and see how it revolutionizes the CICD world. There is no prior experience necessary as we will showcase how easy our platform is to use. You will learn how to use Harness to build out a pipeline and deploy applications without the need for manual scripts.

You’ll have the opportunity to:

* Set up and Harness Delegate and add an EKS Cluster
* Deploy an instance of Prometheus
* Create a successful deployment in Harness using a pipeline and prometheus to monitor the application
* Learn how Harness makes the deployment process easier
* Join the on demand Q&A with your Harness and AWS peers

## What will you learn?:

After the completion of this workshop you will be able to:

* Explain and implement a canary deployment with Harness
* Connect your Harness delegate with AWS
* Deploy a monitoring tool to Harness
* Create a successful deployment pipeline

## Moving Pieces

There will be a few moving pieces. 

* An Amazon EKS Cluster with the ability to deploy
* A Harness Account in which you [can sign up here](http://bit.ly/harness-aws-workshop)
* A GitHub Account
* A fork of https://github.com/ravilach/harness-canary-workshop

## Description

During the deployment, you will be deploying a stable then unstable version of the [Sample Application](https://hub.docker.com/r/harness/cv-demo) to show the virtues of an automated canary deployment. 

Prometheus will be used to automate the canary deployment as the primary source of metric verification. The lab will walk through installing and configuring Prometheus.
