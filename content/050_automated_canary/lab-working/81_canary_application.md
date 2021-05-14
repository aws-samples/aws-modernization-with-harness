---
title: "4.1 Canary Application"
chapter: true
draft: false
weight: 20
---

# Define Sample Application

Similar to deploying Prometheus, create a new Harness Service. 

**Setup -> AWS Canary -> Services + Add Service**

* **Name:** ***Sample App***
* **Deployment Type:** ***Kubernetes***

![Add Application Service](/images/new_service.png)

Click **Submit**. Now click **+Add Artifact Source** and choose **Docker Registry** in the Service Overview Section. 

* **Source Server:** ***Harness Docker Hub*** [public Docker Hub]
* **Docker Image Name:** ***harness/cv-demo***

![Add Artifact Source](/images/artifact_source.png)
 
Once you click **Submit**, before importing the YAMLs in, one modification is needed. 

In the Forked Sample Application Folder GitHub, make modification to the *sample_application/values.yaml*. The change needed is to configure Prometheus which you installed  as an Allowed Origin. 

**ALLOWED_ORIGINS**: <i><http://_elb_address:8080/></i></p>
<i>e.g http://a8241cbf8317f4c1ab5507fbce9d576c-671821569.us-east-2.elb.amazonaws.com:8080/</i>

![Commit the change to git](/images/allowed_origins_commit_2.png)

**Commit** the Change to your Fork

![Committed change](/images/allowed_origins_commit.png)


After the Commit, change back to the Sample App to **Link Remote Manifests**. 

**Setup -> AWS Canary Lab -> Services -> Sample App**

![Sample App Setup](/images/sample_app_setup.png)


Then enter the Remote Manifest Details

* **Manifest Format:** ***Kubernetes Resource***
* **Source Repository:** ***AWS Workshop***
* **Branch:** ***main***
* **File/Folder:** ***sample_application***

![Configure Sample App Remote Manifest](/images/sample_app_remote_manifest.png)

Click **Submit** and you are ready to configure the canary. 

