---
title: "Automated Canary Analysis"
chapter: true
draft: false
weight: 20
---

# Automated Canary Analysis Configuration

With all of the CD Abstraction pieces out of the way, now it is time to define the Workflow which will power the canary analysis. 

Create a new Workflow for the Sample App. 

Setup -> AWS Canary Lab -> Workflows + Add Workflow

Name: Sample App Canary
Workflow Type: Canary Deployment
Environment: The EKS Cluster

![Create Sample App Workflow](../images/sample_app_workflow.png)

Once you hit Submit, can add a canary phase under “Deployment Phases” with + Add Phase

![Sample App Canary](../images/sample_app_canary.png)


In the Phase definition, select the Sample App Service and your Infrastructure Definition.

![Sample App Add Workflow Phase](../images/sample_app_workflow_phase.png)

Once you hit Submit, your Canary Phase will be empty. This step will be filling out the Prometheus Details.

![Sample App Canary phase setup](../images/sample_app_canary_setup.png)

In the Verify section, click + Add Step. Search for “prom” as a function to add. 

![Add Prometheus Step](../images/sample_app_workflow_cv_step.png)

Select Prometheus and then click next. This is where the Prometheus queries will be entered. 

Prometheus Server: EKS Prometheus
Metric Name: normal_call
Metric Type: Throughput
Group Name: custom
Query: io_harness_custom_metric_normal_call{kubernetes_pod_name="$hostName"}

![Configure Prometheus CV](../images/sample_app_configure_prometheus.png)

Add another metric for Errors with + Add
Metric Name: error_call
Metric Type: Error
Group Name: custom
Query: io_harness_custom_metric_error_call{kubernetes_pod_name="$hostName"}

![Configure Prometheus metric](../images/sample_app_configure_prometheus_metric.png)

Then set the Analysis Time to 5 mins and Algorithm to Sensitive. 

![Configure Analysis](../images/sample_app_cv_setup.png)

When completed it should look like this. 

![Prometheus Configuration completed](../images/sample_app_configure_prom_complete.png)

Click Submit and you now have Prometheus added to analyze the canary. 

![Canary Phase Complete](../images/sample_app_workflow_cv.png)

As a good practice, can automate the removal of the resources if the canary should fail. On the right hand side under Rollback Steps, in the Deploy Phase, + Add Step.

![Configure Rollback](../images/sample_app_workflow_rollback.png)

Search for Del for the Delete Step.

![Add Delete step to workflow](../images/sample_app_delete_step.png)

Select Delete.
Resources: ${k8s.canaryWorkload}

![Configure Delete Step](../images/sample_app_workflow_configure_del.png)

Hit Submit and the final canary should look like this. 

![Completed Sample App Workflow](../images/sample_app_workflow_complete.png)

Now you are ready to deploy your application.
