---
title: "Canary Lab"
Chapter: true
draft: false
weight: 30
---
# Your First Automated Canary Deployment in EKS

Welcome to your first automated canary deployment in EKS/Kubernetes by leveraging the [Harness Platform](https://harness.io/platform/).  During the deployment, you will be deploying a stable then unstable version of the [Sample Application](https://hub.docker.com/r/harness/cv-demo) to demonstrate the virtues of an automated canary deployment.

[Prometheus](https://prometheus.io/) will be used to automate as the primary source of metric verification for the canary deployment. The lab will walk through installing and configuring [Prometheus](https://prometheus.io/) as well as configuring the Harness pipeline to validate a good deployment.

In this section, we'll cover the following topics:

{{% children showhidden="false" %}}
