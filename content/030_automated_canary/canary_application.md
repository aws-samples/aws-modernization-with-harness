---
title: "Sample Application"
chapter: true
draft: false
weight: 10
---

# Define Sample Application

With the Prometheus Infrastructure items out of the way, time to focus on deploying an application. Similar to deploying Prometheus, create a new Harness Service. 

Setup -> AWS Canary -> Services + Add Service 
Name: Sample App
Deployment Type: Kubernetes

![Add Application Service](../images/new_service.png)

Hit Submit. Now can add an artifact Source in the Service Overview Section. 

Source Server: Harness Docker Hub [public Docker Hub]
Docker Image Name: harness/cv-demo

![Add Artifact Source](../images/artifact_source.png)
 
Hit submit and can adjust the Kubernetes Resources. For ease, is stored on GitHub. 

Ravi Note: Decision Point: Can the students clone a GitHub repository? This would be for access to the Sample App Files to mainly change the allowed origin. 

Once you hit Submit, before importing the YAMLs in, one modification is needed. 

In the Sample Application Folder GitHub, make modification to the sample_application/values.yaml. The change needed is to configure Prometheus which you installed  as an Allowed Origin. 

ALLOWED_ORIGINS: <http://_elb_address:8080/> e.g http://a8241cbf8317f4c1ab5507fbce9d576c-671821569.us-east-2.elb.amazonaws.com:8080/

![Allowed Origins](../images/allowed_origins.png)


 ## Commit the Change. 

![Commit the change to git](../images/allowed_origins_commit.png)


After the Commit, Back in the Sample App, Link to Remote Manifests. 

Setup -> AWS Canary Lab -> Services -> Sample App

![Sample App Setup](../images/sample_app_setup.png)


Then enter the Remote Manifest Details. 
Manifest Format: Kubernetes Resource
Source Repository: AWS Workshop
Branch:Master
File/Folder: static/yamls/sample_application

![Configure Sample App Remote Manifest](../images/sample_app_remote_manifest.png)

Click Submit and you are ready to configure the canary. 

