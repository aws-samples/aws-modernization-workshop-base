#Workshop developer self-review

> AWS Marketplace specific requirements
1. /_index.md - Change the href url to **Available in MP Link** and the png image to **Seller badge (image)**. Be sure to put the png file you receive into the folder /static/
2. /030_self_guided_setup/request_credit.md - Change ```https://pages.awscloud.com/awsmp-wsm-dev-workshop-series-credit-request.html?trk=lab_{partnerName}``` to the provided **Credit request link**. On the same page change ```https://aws.amazon.com/marketplace/pp/B07PZY3369?&trk=el_a134p000003yrYeAAI&trkCampaign=AWSMP_pdp_dev_x_dg&sc_channel=el&sc_campaign=el_awsmp_mult&sc_outcome=Marketplace``` to the Available in MP link.
3. /099_survey/_index.md - Change ```https://pages.awscloud.com/awsmp-wsm-dev-workshop-series-csat-lab-completion.html``` to the ***CSAT form URL**.
4. ALL workshops part of AWS Marketplace DevOps series need to use your company's free trial Marketplace offer, as part of the workshop. [Free Trial Example](https://aws.amazon.com/marketplace/seller-profile?id=56345c10-b815-46b5-acd2-d0e0d2626670). DO NOT use your company's free trial sign-up page.

> General workshop
1. Has anyone else reviewed the workshop and provided feedback?
2. Have you checked all the links to validate they work?
3. Can you complete the workshop from start to finish without errors?
4. Does the introduction warn of any costs that may be incurred by the customer?
5. Did you update/change the repo's README.md to be about this workshop?
6. Did you edit config.toml and update the workshop title?
7. Is the information in the workshop factually correct?
8. Have you checked spelling and grammar?
9. Is hugo-theme-learn a submodule? The learn theme needs to be a submodule in the repo. To create this cd or create a themes folder. Run ```git submodule add https://github.com/matcornic/hugo-theme-learn.git``` inside the themes folder/directory.

> Introduction
1. Is there an introduction that states what will be covered in the workshop?
1. Does the introduction give an expected duration?
1.  Does the introduction state the outcomes?
1. Does the introduction describe the target audience? 
1. Does the introduction list or describe any necessary background knowledge? For example, a workshop that deals with databases may need some knowledge of basic SQL commands. A workshop on front-end may require knowledge of Javascript, node.js v14 installed, etc.

> Environment
1. If the workshop supports using a customer’s own account, does the workshop describe how to create pre-requisite infrastructure (eg via a CloudFormation, CDK, SAM template, etc) with instructions on how to deploy it?
2. If the workshop integrates with Event Engine, does the workshop include instructions on how to log in via EE. Similarly, if the workshop supports other systems (Qwiklabs, etc) it should provide login instructions for those.
3. If the workshop can only use Event Engine, does the front page clearly state that the workshop can only be used at AWS-run events?
4. Does the workshop include steps to set up local prerequisites? For example, an attendee may need to install things like node, python, an SSH client, or a Cloud9 environment, etc.
If the workshop runs only in specific regions, are these clearly listed?
 
> Cleanup
1. Does the workshop provide instructions on how to clean up resources created during the workshop?
2. Are the instructions at the right level of detail? For example, a 100-level workshop may need to walk a customer through all steps of terminating an EC2 instance. A 400-level workshop may simply tell a user to terminate EC2 instances the user created during the workshop.
3. Are the clean-up steps specific to the resources created in the workshop? Generalisations like “terminate all EC2 instances” could have unintended consequences.
4. Are the steps specific to the user? If more than one person is sharing an AWS account, generalisations like “terminate all EC2 instances” could have unintended consequences.
5. Are deliberately retained resources explained? For example, the workshop may deliberately retain an S3 bucket holding the results of a process.
6. If resources are being retained, is there an explicit comment about costs those resources may incur?
7. If clean-up instructions ask the user to delete a CloudFormation Stack, does this delete all resources in the stack? 
•	CloudFormation stack deletion fail to remove some resources, like non-empty S3 buckets. These could then incur ongoing costs and/or raise possible future security risks.
•	Often a stack provides a workshop’s starting state, and other resources are then created via the console.
8. Does the workshop reference/link to the clean-up steps in the introduction or setup chapters? If someone cannot complete the workshop, they should still know about the existence of clean-up steps. They should not need to complete the workshop before being told of clean-up steps.

> External Links and Privacy
1. Are images and other single files (CloudFormation templates, individual code files, etc) contained within the workshop structure, either within the specific chapter or under the /static folder. For example, an image should use a format like ![](../static/image.png) and not ![](https://googleimagesearch.com/?term=penguin)
2. Do links to any Youtube videos use the Hugo “Youtube” shortcode? (This allows us to enforce privacy-enhanced mode when linking to the content)
3. Is the workshop self-contained? (Will the workshop function/can it be delivered if your personal accounts are lost)

