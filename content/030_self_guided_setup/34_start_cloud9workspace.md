---
title: "3. Create a Workspace"
chapter: true
weight: 14
---

## Set up the Workspace

[AWS Cloud9](https://aws.amazon.com/cloud9/) is a cloud-based integrated development environment (IDE) that lets you write, run, and debug your code with just a browser. It includes a code editor, debugger, and terminal. Cloud9 comes prepackaged with essential tools for popular programming languages, including JavaScript, Python, PHP, and more, so you don’t need to install files or configure your laptop for this workshop.

We will use Amazon Cloud9 to access our AWS accounts via the AWS CLI in this Workshop.  There are a few steps to complete to set this up

1. Create a new Cloud9 IDE environment
1. Create an EKS cluster
1. Configure workshop specific requirements


## Create a new Cloud9 IDE environment

1 . Within the AWS console, use the region drop list to select **us-east-1 (N. Virginia)**.  This will ensure the workshop script provisions the resources in this same region..

2 . Navigate to the [Cloud9 console](https://console.aws.amazon.com/cloud9/home) or just search for it under the **AWS console services** menu.

3 . Click the **Create environment** button

4 . For the name use `partnerName-workshop`, then click **Next step**

5 . Select the default instance type **t3.micro**

6 . Leave all the other settings as default and click **Next step** followed by **Create environment**

<img src=/images/setup/c9create.png>

{{% notice info %}}
This will take about 1-2 minutes to provision
{{% /notice %}}

### Configure Cloud9 IDE environment

When the environment comes up, customize the environment by:

1. Close the **welcome page** tab

1. Close the **lower work area** tab

1. Open a new **terminal** tab in the main work area.

{{% notice tip %}}
If you don't like this dark theme, you can change it from the **View / Themes** Cloud9 workspace menu.
{{% /notice %}}

{{% notice tip %}}
Cloud9 requires third-party-cookies. You can whitelist the [specific domains](https://docs.aws.amazon.com/cloud9/latest/user-guide/troubleshooting.html#troubleshooting-env-loading).  You are having issues with this, Ad blockers, javascript disablers, and tracking blockers should be disabled for the cloud9 domain, or connecting to the workspace might be impacted.
{{% /notice %}}
