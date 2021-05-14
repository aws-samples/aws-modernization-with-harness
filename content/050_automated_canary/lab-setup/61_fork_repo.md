---
title: "2.1 Fork Workshop Repo"
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

* **Name:** ***AWS Workshop***
* **URL:** ***https://github.com/[YOUR-GITHUB-ACCOUNT]/harness-canary-workshop (your Forked address)***
* **Username:** ***Your Github User Name***
* **Password/Secret:** ***Select '+ Create Encrypted Text' to add your token/pw as a Harness Secret***

![Add Git Connector](/images/aws_git_connector.png)

  Add your encrypted secret

![Add Git Secret](/images/git_encrypted_secret.png)

{{% notice note %}} 
For your git secret, you can either encrypt either your github password or create a Personal Access Token in your github account and use it in place of your password to access the git resources.  For more information on creating a Personal Access Token, please click [here](https://docs.github.com/en/github/authenticating-to-github/creating-a-personal-access-token).
{{% /notice %}}

When you are finished, click **Submit** to save the secret configuration and **Submit** again to save the Git Connector.  Once completed the Repository is added. 
