---
title: "Create a Workspace" # MODIFY THIS TITLE
chapter: true
weight: 2 # MODIFY THIS VALUE TO REFLECT THE ORDERING OF THE MODULES
---

<!-- MORE SUBMODULES CAN BE ADDED TO DIVIDE UP THE SETUP INTO SMALLER SECTIONS -->
<!-- COPY AND PASTE THIS SUBMODULE FILE, RENAME, AND CHANGE THE CONTENTS AS NECESSARY -->


# Set Up The Workspace <!-- MODIFY THIS SUBHEADING -->

## Submodule Two Heading <!-- MODIFY THIS SUBHEADING -->

This paragraph block can be used to explain how to create a workspace if necessary. Example content guidance can be found at the bottom of the page.

{{% notice info %}}
<p style='text-align: left;'>
**REMOVE:** With the exception of _index.md, the module folders and filenames should be changed to better reflect their content, i.e. 1_Planning as the folder and 11_HowToBegin as the first submodule. Changing the "weight" value of the header is ultimately what reflects the order the modules are presented.
</p>
{{% /notice %}}

### Next Section Heading <!-- MODIFY THIS HEADING -->
This paragraph block can optionally be utilized to lead into the next section of the workshop.

#### Example Content Guidance

# Set Up Your Workspace
AWS Cloud9 is a cloud-based integrated development environment (IDE) that lets you write, run, and debug your code with just a browser. It includes a code editor, debugger, and terminal. Cloud9 comes prepackaged with essential tools for popular programming languages, including JavaScript, Python, PHP, and more, so you don’t need to install files or configure your laptop for this workshop.

We will use Amazon Cloud9 to access our AWS accounts via the AWS CLI in this Workshop. There are a few steps to complete to set this up

    Create a new Cloud9 IDE environment
    Create an IAM role for your workspace
    Attach the IAM role to your workspace
    Configure workshop specific requirements


### Create a new Cloud9 IDE environment <!-- MODIFY THIS SUBHEADING -->

    Within the AWS console, use the region drop list to select us-east-1 (N. Virginia). This will ensure the workshop script provisions the resources in this same region..

    Navigate to the Cloud9 console or just search for it under the AWS console services menu.

    Click the Create environment button

    For the name use circleci-workshop, then click Next step

    Select the default instance type t2.micro

    Leave all the other settings as default and click Next step followed by Create environment

Info: This will take about 1-2 minutes to provision


### Configure Cloud9 IDE environment <!-- MODIFY THIS SUBHEADING -->

When the environment comes up, customize the environment by:

    Close the welcome page tab

    Close the lower work area tab

    Open a new terminal tab in the main work area.

Tip: If you don’t like this dark theme, you can change it from the View / Themes Cloud9 workspace menu.

Tip: Cloud9 requires third-party-cookies. You can whitelist the specific domains. You are having issues with this, Ad blockers, javascript disabler, and tracking blockers should be disabled for the cloud9 domain, or connecting to the workspace might be impacted.
