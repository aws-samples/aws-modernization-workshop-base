---
title: "Attach IAM Role" # MODIFY THIS TITLE
chapter: true
weight: 4 # MODIFY THIS VALUE TO REFLECT THE ORDERING OF THE MODULES
---

<!-- MORE SUBMODULES CAN BE ADDED TO DIVIDE UP THE SETUP INTO SMALLER SECTIONS -->
<!-- COPY AND PASTE THIS SUBMODULE FILE, RENAME, AND CHANGE THE CONTENTS AS NECESSARY -->


### Attach the IAM role to your instance <!-- MODIFY THIS SUBHEADING -->
Will need

    Follow this deep link to find your Cloud9 EC2 instance
    (https://console.aws.amazon.com/ec2/v2/home?region=us-east-1#Instances:search=aws-cloud9-circleci-workshop;sort=desc:launchTime)

    Select the instance, then choose Actions / Security / Modify IAM role Attach IAM role

    Choose the role that we created in the previous step: CircleCI-Workshop-Admin. Find IAM role

    Click Save
