---
title: "2. Running the workshop on your own"
chapter: true
weight: 16
---

# AWS Setup

{{< marketo-script >}}

{{% notice warning %}}
This account will expire at the end of the workshop and all the resources created will be automatically de-provisioned. You will not be able to access this account after today.
{{% /notice %}}

{{% notice warning %}}

Only complete this section if you are running the workshop on your own. If you are at an AWS hosted event (such as re:Invent, Kubecon, Immersion Day, etc), go to [Start the workshop at an AWS event](/20_prerequisites/12_aws_event_setup.html).

{{% /notice %}}

If you are unable to attend an AWS-hosted event, don't worry! You'll still be able to go through this workshop by yourself. To request AWS Credits, please click the [request AWS credit page](/020_prerequisites/aws_setup/23_request_aws_credit.md). 

Below are instructions on how to set up your AWS environment.

{{% children %}}

## Setting up your AWS account

{{% notice warning %}}
Your account must have the ability to create new IAM roles and scope other IAM permissions.
{{% /notice %}}

1. If you don't already have an AWS account with Administrator access: [create
one now by clicking here](https://aws.amazon.com/getting-started/)

1. Once you have an AWS account, ensure you are following the remaining workshop steps
as an IAM user with administrator access to the AWS account:
[Create a new IAM user to use for the workshop](https://console.aws.amazon.com/iam/home?#/users$new)

1. Enter the user details:
![create user](/images/20_prerequisites/iam-1-create-user.png)

1. Attach the AdministratorAccess IAM Policy:
![attach policy](/images/20_prerequisites/iam-2-attach-policy.png)

1. Click to create the new user:
![finish creation](/images/20_prerequisites/iam-3-create-user.png)

1. Take note of the login URL and save:
![login url](/images/20_prerequisites/iam-4-save-url.png)
   
1. Log into your AWS console via the previous login URL and proceed through the rest of the lab.
