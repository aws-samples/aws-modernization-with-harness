---
title: "3.3 Prometheus Deployment"
chapter: true
draft: false
weight: 53
---

## Prometheus Deployment

To deploy something in Harness, defining a Harness Workflow will define the steps on the deployment will be achieved. 

**Setup-> AWS Canary Lab -> Workflows + Add Workflow**

* **Name:** ***Deploy Prometheus***
* **Workflow Type:** ***Rolling Deployment***
* **Environment:** ***The EKS Cluster***
* **Service:** ***Install Prometheus***
* **Infrastructure Definition:** ***My EKS Cluster***

![Configure Prometheus Deployment Workflow](/images/prometheus_workflow.png)

Click **Submit** and you are ready to deploy.

In the upper right hand corner of the Workflow, click **Deploy**.  

![Prometheus Workflow](/images/prometheus_deploy.png)

add a Note if you like for this deployment...

![Deploy Prometheus Service](/images/new_deployment.png)

click **Submit** and Prometheus will be deployed. You will be taken to the Deployments view to observe the deployment of your Prometheus service.

![Deploy Prometheus](/images/deployment_prometheus.png)
