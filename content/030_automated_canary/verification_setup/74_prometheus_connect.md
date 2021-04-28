---
title: "7.4 Connecting Prometheus"
chapter: true
draft: false
weight: 54
---

## Connecting Harness to Prometheus

In order to connect Harness to Prometheus, you need the accessible URL endpoint. To grab the HTTP accessible address, run the following command.

    kubectl describe service prometheus-service

![Prometheus Service Elastic Load Balancer](/images/prometheus_elb.png)

Copy down the LoadBalancer Ingress address from the output of the kubectl command:</p>
***a8241cbf8317f4c1ab5507fbce9d576c-671821569.us-east-2.elb.amazonaws.com***

You can navigate to the Prometheus UI to validate installation by adding port **8080** </p>
**for example:** ***https\://a8241cbf8317f4c1ab5507fbce9d576c-671821569.us-east-2.elb.amazonaws.com:8080***

![Prometheus Console](/images/prometheus_console.png)

Add Prometheus as a Verification Provider
To wire Prometheus to Harness, setup as a Verification Provider. 

**Setup -> Connectors -> Verification Providers + Add Verification Provider -> Prometheus**

* **Display Name:** ***EKS Prometheus***
* **URL:** ***http\://_elb_address:8080/*** </p>
**for example:** ***http\://a8241cbf8317f4c1ab5507fbce9d576c-671821569.us-east-2.elb.amazonaws.com:8080/***

![Add Prometheus Verification Provider](/images/prometheus_provider.png)

Click **Submit** and Prometheus will be wired to Harness.

![Prometheus Provider successfully created ](/images/prometheus_provider_completed.png)
