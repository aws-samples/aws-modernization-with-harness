---
title: "3.2 Prometheus Installation"
chapter: true
draft: false
weight: 52
---

## Prometheus Installation

Harness can facilitate the installation of Prometheus. For this workshop, the Prometheus deployables have been configured to be accessible by the workloads in the  EKS Cluster in the Git Repository. 

**Setup -> AWS Canary Lab -> Services  + Add Service**

* **Name:** ***Install Prometheus***
* **Deployment Type:** ***Kubernetes***

![Add Prometheus Service](/images/prometheus_service.png)

Once you click **Submit**, click on **ellipses** on the right hand side to **Link Remote Manifests**. 

![Setup Prometheus Service](/images/prometheus_service_setup.png)

Enter the following information:

* **Manifest Format:** ***Kubernetes Resource Specs in YAML format***
* **Source Repository:** ***AWS Workshop*** (this is the repo we added earlier)
* **Branch:** ***master***
* **File/Folder:** ***prometheus***

![Configure Remote Manifest](/images/remote_manifest.png)

Click **Submit** and you are ready to deploy Prometheus. 

