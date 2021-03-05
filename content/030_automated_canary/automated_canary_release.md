---
title: "Deploy Your Canary"
chapter: true
draft: false
weight: 30
---

# Deploy Your Canary

It is now time to deploy your application and enjoy safety of an automated canary analysis. 

The sample application has a stable and unstable version to deploy for demonstration. To toggle between the two, will take advantage of Harness Workflow Variables.

Back in the Application, add two Workflow Variables. 

Setup -> AWS Canary Lab -> Workflows -> Sample App Canary

On the bottom right, click on the “Workflow Variables” pencil icon. 

![Workflow Variables](../images/workflow_vars_small.png)


Add a pair of variables. 
First: verify_canary / Text / yes
Second: metric_verification / Text / Prometheus

![Add Workflow Variables](../images/workflow_vars_setup.png)

Click Save, and your Workflow should look like this.

![Canary workflow completed](../images/canary_workflow_complete.png)

The last step is to define what happens after a successful Canay, which would be to promote. Can click on the + Add Phase after the Canary in Deployment Phase. 

Service: Sample App
Infrastructure Definition: My EKS Cluster

![Add Workflow Phase](../images/sample_app_workflow_phase.png)

Once you hit Submit, your Workflow should look like this and you are ready to deploy.

![Completed Canary Workflow setup](../images/sample_app_workflow_primary.png)

Now you are ready to deploy. Click on Deploy on the top right. 
Verify_canary: no
Artifact Build: Tag # stable 

![Start new stable deployment](../images/start_new_deployment.png)

Click Submit and stable/baseline is headed out the door. 

![Sample App stable Deployment](../images/sample_app_deployment.png)

Now for the fun, you can deploy another version of the application. This can represent a change going into production. 

Continuous Deployment -> Deployments -> Start New Deployment 

Application: AWS Canary Lab
Workflow: Sample App Canary
Verify_canary: yes
Artifact Build: #unstable 

![Start new broken deployment](../images/start_new_deployment_broken.png)

Hit Submit and this part will take a few minutes to analyze depending how quickly you redeployed. The learning interval is 5 minutes and the baseline needs to also learn.  

As expected, the canary analysis is expected to fail because of the application being unstable. Just like that, you now have an automated canary deployment. 

![Sample App Deployment unstable](../images/sample_app_deployment_broken.png)

The rollback was completed without any admin or user intervention. 

![Sample App Deployment rolled back](../images/sample_app_deployment_rollback.png)

Happy Deploying!

-The Harness Team
