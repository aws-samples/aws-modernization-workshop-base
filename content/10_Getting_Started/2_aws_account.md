+++
title = "AWS Account"
chapter = false
weight = 2
+++
{{% notice warning %}}
You are responsible for the cost of the AWS services used while running this workshop in your AWS account.
{{% /notice %}}

{{% notice warning %}}
Your account must have the ability to create new IAM roles and scope other IAM permissions.
{{% /notice %}}

{{% notice note %}}
If you already have an AWS account, and have IAM Administrator access, go to 
[Provision VPC & Cloud9]({{< ref "#provision-vpc-and-cloud9" >}})
{{% /notice %}}

## Create an account 

1. If you don't already have an AWS account with Administrator access: [create
one now](http://docs.aws.amazon.com/connect/latest/adminguide/gettingstarted.html#sign-up-for-aws)

2. Once you have an AWS account, ensure you are following the remaining workshop steps
as an **IAM user** with administrator access to the AWS account:
[Create a new IAM user to use for the workshop](https://console.aws.amazon.com/iam/home?region=us-east-1#/users$new)

3. Enter the user details:
![Create User](/images/getting_started/iam-1-create-user.png)

4. Attach the AdministratorAccess IAM Policy:
![Attach Policy](/images/getting_started/iam-2-attach-policy.png)

5. Click to create the new user:
![Confirm User](/images/getting_started/iam-3-create-user.png)

6. Take note of the login URL and save:
![Login URL](/images/getting_started/iam-4-save-url.png)


## Provision VPC 

   [Click here to deploy using CloudFormation template](https://us-west-2.console.aws.amazon.com/cloudformation/home?region=us-west-2#/stacks/create/template?stackName=ModernizationWorkshop-EKS&templateURL=https://modernization-workshop-bucket.s3-us-west-2.amazonaws.com/cfn/master-stacks/vpc-only.yaml)

   - Create stack, click **Next**
   - Specify stack details, click **Next**
   - Configure stack options, click **Next**
   - Review UnicornDevSecOpsWorkshop, scroll to bottom section under **Capabilities** and check both boxes and click **Create stack** 

{{% notice info %}}
The installation takes a few minutes. Please continue to the next section.
{{% /notice %}}
