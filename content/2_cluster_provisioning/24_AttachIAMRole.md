---
title: "Attach IAM Role" # MODIFY THIS TITLE
chapter: true
weight: 4 # MODIFY THIS VALUE TO REFLECT THE ORDERING OF THE MODULES
---

<!-- MORE SUBMODULES CAN BE ADDED TO DIVIDE UP THE SETUP INTO SMALLER SECTIONS -->
<!-- COPY AND PASTE THIS SUBMODULE FILE, RENAME, AND CHANGE THE CONTENTS AS NECESSARY -->

# Attaching an IAM Role

## Submodule Four Heading <!-- MODIFY THIS SUBHEADING -->

This paragraph block can be used to explain how to attach an IAM role if necessary. Example content guidance can be found at the bottom of the page.

{{% notice info %}}
<p style='text-align: left;'>
**REMOVE:** With the exception of _index.md, the module folders and filenames should be changed to better reflect their content, i.e. 1_Planning as the folder and 11_HowToBegin as the first submodule. Changing the "weight" value of the header is ultimately what reflects the order the modules are presented.
</p>
{{% /notice %}}

### Next Section Heading <!-- MODIFY THIS HEADING -->
This paragraph block can optionally be utilized to lead into the next section of the workshop.

#### Example Content Guidance
### Attach the IAM role to your instance <!-- MODIFY THIS SUBHEADING -->
Will need

    Follow this deep link to find your Cloud9 EC2 instance
    (https://console.aws.amazon.com/ec2/v2/home?region=us-east-1#Instances:search=aws-cloud9-circleci-workshop;sort=desc:launchTime)

    Select the instance, then choose Actions / Security / Modify IAM role Attach IAM role

    Choose the role that we created in the previous step: CircleCI-Workshop-Admin. Find IAM role

    Click Save
