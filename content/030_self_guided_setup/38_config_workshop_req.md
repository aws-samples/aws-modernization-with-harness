---
title: "6. Configure workshop specific requirements"
chapter: true
weight: 18
---

## Configure Workspace

{{% notice info %}}
Cloud9 normally manages IAM credentials dynamically. This isn't currently compatible with
the EKS IAM authentication, so we will disable it and rely on the IAM role instead.
{{% /notice %}}

1. Return to your workspace and click the gear icon (in top right corner), or click to open a new tab and choose "Open Preferences"

2. Select **AWS SETTINGS** and turn off **AWS managed temporary credentials**

3. Close the Preferences tab
   
    ![Turn off temp credentials](/images/20_prerequisites/iamRoleWorkspace.gif)

4. Copy and run (paste with **Ctrl+P** or **CMD+P**) the commands below.

      Before running it, review what it does by reading through the comments.

      ```sh
      # Update awscli
      sudo pip install --upgrade awscli && hash -r
      
      # Install jq command-line tool for parsing JSON, and bash-completion
      sudo yum -y install jq gettext bash-completion moreutils
      
      # Install yq for yaml processing
      echo 'yq() {
      docker run --rm -i -v "${PWD}":/workdir mikefarah/yq yq "$@"
      }' | tee -a ~/.bashrc && source ~/.bashrc
      
      # Verify the binaries are in the path and executable
      for command in jq aws
      do
        which $command &>/dev/null && echo "$command in path" || echo "$command NOT FOUND"
      done
      
      # Remove existing credentials file.
      rm -vf ${HOME}/.aws/credentials
      
      # Set the ACCOUNT_ID and the region to work with our desired region
      export AWS_REGION=$(curl -s 169.254.169.254/latest/dynamic/instance-identity/document | jq -r '.region')
      test -n "$AWS_REGION" && echo AWS_REGION is "$AWS_REGION" || echo AWS_REGION is not set
      ```
   
5. Now we'll start installing kubectl and set up our Cloud9 instance to be to connect to the pre-provisioned EKS cluster 
   
      Copy and run (paste with **Ctrl+P** or **CMD+P**) the commands below.

      Before running it, review what it does by reading through the comments.

      ```sh
      # Verify there is an EKS cluster already provisioned, the EKS cluster's name is basic-eks
      aws eks list-clusters --region us-east-1
      
      # Install kubectl binary
      curl -o kubectl https://amazon-eks.s3.us-west-2.amazonaws.com/1.19.6/2021-01-05/bin/linux/amd64/kubectl
      
      # Apply permission to execute binary
      chmod +x ./kubectl
      
      # Copy binary to PATH, which allows you to write kubectl commands in any folder 
      mkdir -p $HOME/bin && cp ./kubectl $HOME/bin/kubectl && export PATH=$HOME/bin:$PATH
      
      #Verify kubectl is installed and can be executed
      kubectl version
      
      # Update the kubeconfig file and point to the Kube API server
      aws eks update-kubeconfig --name basic-eks --region us-east-1
      
      # Verify you are connected to EKS cluster
      kubectl get pods --all-namespaces
      ```
      {{% notice warning %}}
   If the pods cannot be listed, <span style="color: red;">**DO NOT PROCEED**</span>. Please re-confirm the last few steps.
   {{% /notice %}}

   If you are done, please proceed to the Harness Setup section!