---
title: "Verification Setup"
chapter: true
draft: false
weight: 20
---

# Verification Setup

In this step will be deploying the Kubernetes Metrics Server in EKS and Prometheus on the EKS Cluster.
Kubernetes Metrics Server
Installing the Metrics Server can be done in one kubectl command. 
kubectl apply -f https://github.com/kubernetes-sigs/metrics-server/releases/latest/download/components.yaml

![kubctl apply metrics server](../images/images/install_metrics_server.png)

## Prometheus Installation

Harness can facilitate the installation of Prometheus. For this workshop, the Prometheus deployables have been configured to be accessible by the workloads in the  EKS Cluster in the Git Repository. 

Setup -> AWS Canary Lab -> Services  + Add Service
Name: Install Prometheus 
Deployment Type: Kubernetes

![Add Prometheus Service](../images/prometheus_service.png)

Once you hit Submit, click on three ellipses on the right hand side to Link Remote Manifests. 

![Setup Prometheus Service](../images/prometheus_service_setup.png)

Enter the following information:
Manifest Format: Kubernetes Specs
Source Repository: AWS Workshop
Branch: master
File/Folder: static/yamls/prometheus

![Configure Remote Manifest](../images/remote_manifest.png)

Click Submit and you are ready to deploy Prometheus. 

## Prometheus Deployment

To deploy something in Harness, defining a Harness Workflow will define the steps on the deployment will be achieved. 

Setup-> AWS Canary Lab -> Workflows + Add Workflow
Name: Deploy Prometheus
Workflow Type: Rolling Deployment
Environment: The EKS Cluster
Service: Install Prometheus
Infrastructure Definition: My EKS Cluster

![Configure Prometheus Deployment Workflow](../images/prometheus_workflow.png)

Click Submit and you are ready to deploy.

In the upper right hand corner of the Workflow, click Deploy.  

![Deploy Prometheus Service](../images/new_deployment.png)

Hit Submit and Prometheus will be deployed. 

![Deploy Prometheus](../images/deployment_prometheus.png)

## Get Prometheus ELB Address

To grab the HTTP accessible address for Prometheus, run the following command.

kubectl describe service prometheus-service

![Prometheus Service Elastic Load Balancer](../images/prometheus_elb.png)

Copy down the LoadBalancer Ingress address.
E.g a8241cbf8317f4c1ab5507fbce9d576c-671821569.us-east-2.elb.amazonaws.com
You can navigate to the Prometheus UI to validate installation by adding port 8080. 
E.g a8241cbf8317f4c1ab5507fbce9d576c-671821569.us-east-2.elb.amazonaws.com:8080

![Prometheus Console](../images/prometheus_console.png)

Add Prometheus as a Verification Provider
To wire Prometheus to Harness, setup as a Verification Provider. 

Setup -> Connectors -> Verification Providers + Add Verification Provider -> Prometheus
Display Name: EKS Prometheus 
URL: <http://_elb_address:8080/> e.g http://a8241cbf8317f4c1ab5507fbce9d576c-671821569.us-east-2.elb.amazonaws.com:8080/

![Add Prometheus Verification Provider](../images/prometheus_provider.png)

Click Submit and Prometheus will be wired to Harness.

![Prometheus Provider successfully created ](../images/prometheus_provider_completed.png)
