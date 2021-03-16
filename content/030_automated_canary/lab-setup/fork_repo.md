---
title: "7.1 Fork Workshop Repo"
chapter: true
draft: false
weight: 20
---

## Fork and Add Workshop GitHub Repository to Harness
Fork this [GitHub Repository](https://github.com/ravilach/harness-canary-workshop) into your
own account. When referring to the git configuration YAMLs, please refer to your Forked
repository. While logged into GitHub, visit https://github.com/ravilach/harness-canary-workshop
and click Fork.

![Fork Github repo](/images/fork_repo.png)

Adding your newly forked repository will allow for workshop assets to be used in Harness. 

**Setup -> Connectors -> Source Repo Providers + Add Source Repo Provider**

* Name: AWS Workshop
* URL: https://github.com/ravilach/harness-canary-workshop (your Forked address)
* Username: Your User Name
* Password/Secret: Click Pencil to add your token/pw as a Harness Secret

![Add Git Connector](/images/aws_git_connector.png)

Click Submit and the Repository is added. 