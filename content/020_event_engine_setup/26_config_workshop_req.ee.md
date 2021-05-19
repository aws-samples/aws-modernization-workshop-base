---
title: "4. Configure workshop specific requirements"
chapter: true
weight: 16
---

## Configure Workspace

{{% notice info %}}
Cloud9 normally manages IAM credentials dynamically. This isn't currently compatible with
the EKS IAM authentication, so we will disable it and rely on the IAM role instead.
{{% /notice %}}

1. Return to your workspace and click the gear icon (in top right corner), or click to open a new tab and choose "Open Preferences"

2. Select **AWS SETTINGS** and turn off **AWS managed temporary credentials**

3. Close the Preferences tab
   
    ![Turn off temp credentials](/images/setup/iamRoleWorkspace.gif)

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
      
      # Validate that our IAM role is valid.
      aws sts get-caller-identity --query Arn | grep BastionRole -q && echo "IAM role valid" || echo "IAM role NOT valid"
      ```

      {{% notice warning %}}
   If the IAM role is not valid, <span style="color: red;">**DO NOT PROCEED**</span>. Go back and confirm the steps on this page.
   {{% /notice %}}

If you have completed the above instructions, please  move to the Partner Setup section!
