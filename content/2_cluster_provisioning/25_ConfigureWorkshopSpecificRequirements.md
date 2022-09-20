---
title: "Configure workshop specific requirements" # MODIFY THIS TITLE
chapter: true
weight: 5 # MODIFY THIS VALUE TO REFLECT THE ORDERING OF THE MODULES
---

<!-- MORE SUBMODULES CAN BE ADDED TO DIVIDE UP THE SETUP INTO SMALLER SECTIONS -->
<!-- COPY AND PASTE THIS SUBMODULE FILE, RENAME, AND CHANGE THE CONTENTS AS NECESSARY -->

# Configuring Workshop Specific Requirements <!-- MODIFY THIS HEADING IF NECESSARY -->

## Submodule Five Heading <!-- MODIFY THIS SUBHEADING -->

This paragraph block can be used to explain how to configure any specific workshop requirements if necessary. Example content guidance can be found at the bottom of the page.

{{% notice info %}}
<p style='text-align: left;'>
**REMOVE:** With the exception of _index.md, the module folders and filenames should be changed to better reflect their content, i.e. 1_Planning as the folder and 11_HowToBegin as the first submodule. Changing the "weight" value of the header is ultimately what reflects the order the modules are presented.
</p>
{{% /notice %}}

### Next Section Heading <!-- MODIFY THIS HEADING -->
This paragraph block can optionally be utilized to lead into the next section of the workshop.


#### Example Content Guidance
# Configure Workspace <!-- MODIFY THIS SUBHEADING -->

    Return to your workspace and click the gear icon (in top right corner), or click to open a new tab and choose “Open Preferences”

    Select AWS SETTINGS and turn off AWS managed temporary credentials

    Close the Preferences tab

Turn off temp credentials

    Copy and run (paste with Ctrl+P or CMD+P) the commands below.

Before running it, review what it does by reading through the comments.

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
aws sts get-caller-identity --query Arn | grep CircleCI-Workshop-Admin -q && echo "IAM role valid" || echo "IAM role NOT valid"

## Warning If the IAM role is not valid, DO NOT PROCEED. Go back and confirm the steps on this page.
