---
title: Using Your Own AWS Account
weight: 20
---

::alert[If you are participating in an AWS guided event, your instructor will have given you access to an AWS account provisioned exclusively for this workshop through Workshop Studio. [Click here](/03-getting-started/01-aws-event) for instructions for joining an AWS guided event.]{header=Note}

## Workshop resources

The following resources will be deployed to run the workshop:

- AWS Cloud9 environment named **Workshop**.
- AWS CodeCommit repository named **Workshop**, populated with template code.

To configure the Cloud9 environment, a number of additional resources are provisioned.

- AWS Systems Manager Automation Document used to configure the Cloud9 environment.
- Amazon S3 bucket to hold the Automation Document's output logs.
- AWS Lambda function to create a CloudFormation template to associate the Automation Document with the Cloud9 environment.
- IAM roles for the Lambda function.

:::alert{header=Note}
The role used to bootstrap the account will require sufficient permissions to provision the resources above.
:::

## Download and execute the bootstrap script

We will download the CloudFormation templates used to provision the resources, and the bootstrap script to run the templates. We will then run the bootstrap script to provision the resources.

1. Sign in to the AWS Management Console and open the AWS CloudShell console at https://console.aws.amazon.com/cloudshell/.

2. In the menu bar, for **Select a Region**, choose the region in which you will be running the workshop.

![Select Region](/static/images/own-account/select-region.png)
3. Run the following code in CloudShell terminal.

:::code{showCopyAction=true showLineNumbers=false language=bash}

# Download code Zip file

curl ':assetUrl{path="/code/workshop.zip" source=s3}' -o workshop.zip

# Download CloudFormation templates

curl ':assetUrl{path="/cfn/cloud9.yaml" source=repo}' -o cloud9.yaml
curl ':assetUrl{path="/cfn/codecommit.yaml" source=repo}' -o codecommit.yaml

# Download bootstrap script

curl ':assetUrl{path="/scripts/own_account.sh" source=repo}' -o own_account.sh
:::
5. On the **Safe Paste** dialog, choose **Paste**.
6. Run the bootstrap script in the CloudShell terminal.

:::code{showCopyAction=true showLineNumbers=false language=bash}
sh own_account.sh
:::

:::alert{header=Note}
The Cloud9 deployment and setup process takes approximately 5 minutes to complete.
:::

:::alert{header="Important" type="warning"}
If you are running this workshop on your own AWS account, remember to delete all resources by following the [Cleanup instructions](/90-cleanup) to avoid unnecessary charges.
:::
