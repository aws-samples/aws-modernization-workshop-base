### MP DevOps Series Specific – Skip section if not part of MP DevOps series

|
 | **Yes/No/Comments** |
| --- | --- |
| Is the main page seller badge correct? |
 |
| Does the seller badge link to the sellers page in Marketplace |
 |
| On the credit request page, does the request credit link to the correct page, URL should have partners name at the end? On the same page does the available in MP link to correct partners page? |
 |
| Does the survey link do to the correct URL? |
 |
| Does the workshop use the Marketplace free trial listing? |
 |

###

### Workshop general

|
 | **Yes/No/Comments** |
| --- | --- |
| Is hugo-theme-learn a submodule? The learn theme needs to be a submodule in the repo. To create this cd or create a themes folder. Run ```git submodule add https://github.com/matcornic/hugo-theme-learn.git``` inside the themes folder/directory. |
 |
| Did you update/change the repo&#39;s README.md to be about this workshop? |
 |
| Did you edit config.toml and update the workshop title? |
 |

###

###

### Workshop introduction

|
 | **Yes/No/Comments** |
| --- | --- |
| Is there an introduction that states what will be covered in the workshop? |
 |
| Does the introduction give an expected duration? |
 |
| Does the introduction state the outcomes? (ie what someone completing the workshop will learn) |
 |
| Does the introduction describe the target audience? |
 |
| sd |
 |
| Does the introduction warn of any costs that may be incurred by the customer? |
 |

### Environment setup

|
 | **Yes/No/Comments** |
| --- | --- |
| AWS Account Access |
 |
| If the workshop supports using a customer&#39;s own account, does the workshop describe how to create pre-requisite infrastructure (eg via a CloudFormation, CDK, SAM template, etc) with instructions on how to deploy it? |
 |
| If the workshop integrates with Event Engine, does the workshop include instructions on how to log in via EE. Similarly, if the workshop supports other systems (Qwiklabs, etc) it should provide login instructions for those. |
 |
| If the workshop can _only_ use Event Engine, does the front page clearly state that the workshop can only be used at AWS-run events? |
 |
| Does the workshop include steps to set up local prerequisites? For example, an attendee may need to install things like node, python, an SSH client, or a Cloud9 environment, etc. |
 |
| If the workshop runs only in specific regions, are these clearly listed? |
 |

### Environment clean-up

|
 | **Yes/No/Comments** |
| --- | --- |
| Does the workshop provide instructions on how to clean up resources created during the workshop? |
 |
| Are the instructions at the right level of detail? For example, a 100-level workshop may need to walk a customer through all steps of terminating an EC2 instance. A 400-level workshop may simply tell a user to terminate EC2 instances the user created during the workshop. |
 |
| Are the clean-up steps specific to the resources created in the workshop? Generalisations like &quot;terminate all EC2 instances&quot; could have unintended consequences. |
 |
| Are the steps specific to the user? If more than one person is sharing an AWS account, generalisations like &quot;terminate all EC2 instances&quot; could have unintended consequences. |
 |
| Are deliberately retained resources explained? For example, the workshop may deliberately retain an S3 bucket holding the results of a process. |
 |
| If resources are being retained, is there an explicit comment about costs those resources may incur? |
 |
| If clean-up instructions ask the user to delete a CloudFormation Stack, does this delete all resources in the stack?
- CloudFormation stack deletion fail to remove some resources, like non-empty S3 buckets. These could then incur ongoing costs and/or raise possible future security risks.
- Often a stack provides a workshop&#39;s starting state, and other resources are then created via the console.
 |
 |
| Does the workshop reference/link to the clean-up steps in the introduction or setup chapters? If someone cannot complete the workshop, they should still know about the existence of clean-up steps. They should not need to complete the workshop before being told of clean-up steps. |
 |

### Well-architected workshop infrastructure

The workshop should adhere to AWS Well-Architected principles where practical

|
 | **Yes/No/Comments** |
| --- | --- |
| Are resources deployed in multiple availability zones? |
 |
| Will resources scale with demand? For example: are EC2 instances deployed within an ASG? |
 |
| For any resources that are not deployed in a redundant, scalable, cost-efficient manner: Is there a comment that this choice is deliberate? |
 |

### External links and privacy

Workshop materials should be self-contained wherever practical.

|
 | **Yes/No/Comments** |
| --- | --- |
| Are images and other single files (CloudFormation templates, individual code files, etc) contained within the workshop structure, either within the specific chapter or under the /static folder. For example, an image should use a format like ![](../static/image.png) and not ![]([https://googleimagesearch.com/?term=penguin](https://googleimagesearch.com/?term=penguin)) |
 |
| Do all images used in this workshop have a [CC0 license](https://creativecommons.org/share-your-work/public-domain/cc0/)? |
 |
| If the workshop references larger bundles of AWS-owned content (for example Lambda source code, sample data sets, etc), are these stored somewhere central like an Event Engine S3 bucket, or an AWS-owned Github Organization (AWS-Samples etc, see Open Source below)?
- Resources _must not_ be hosted in individually-owned AWS accounts, individual Github accounts, etc.
 |
 |
| Do links to any Youtube videos use the Hugo &quot;Youtube&quot; shortcode? (This allows us to enforce privacy-enhanced mode when linking to the content) |
 |
| Are all included data sets comprised of fake data or open data sets held in places like [https://registry.opendata.aws/](https://registry.opendata.aws/) (Third party data sets can be referenced in the workshop but should not be included)
 |
 |
| Is the workshop self-contained? (Will the workshop function/can it be delivered if your personal accounts are lost) |
 |

### Security

|
 | **Yes/No/Comments** |
| --- | --- |
| Confirm the content does not reference any confidential information, internal tools, or internal-only jargon. (e.g.; internal Amazon systems, employee information, containment scores, etc)s |
 |
| If IAM Users or Roles are created, do they have appropriately scoped policies? IAM principals should use AWS-managed policies unless there&#39;s a specific need for a custom policy. |
 |
| Do S3 Buckets restrict public access, either via _S3 Block Public Access_ or an S3 Bucket Policy? |
 |
| Do EC2 Security Groups restrict access to specific source IPs and ports? |
 |
| Do RDS instances have Public Access disabled? |
 |
| For configurations that don&#39;t adhere to AWS Well-Architected practices, is there a note that explains why this is done, and a recommendation for a best-practice approach? |
 |
| Does sample code (eg Lambda functions) perform only the required actions? |
 |
| Does sample code run using an IAM role that allows only required actions? |
 |
| If attendees are asked to enter information, is this anonymised? Personally Identifiable Information (PII) should be avoided unless _strictly_ necessary (for example testing SES may require the attendees enter a valid email address to receive an email). |
 |

### Source code, sample data, third party sources, and Open Source

|
 | **Yes/No/Comments** |
| --- | --- |
| If the workshop includes any AWS-created code (eg Lambda functions) does the code include a license? The [MIT-0 license](https://github.com/aws/mit-0) is a good choice for workshop sample code that is not intended for production use. |
 |
| Third-party code should be referenced rather than included whenever possible, but when third-party code must be included that code&#39;s license must allow for Amazon/AWS usage and the workshop should include attribution. If you&#39;re unsure, contact the Open Source team here: [https://w.amazon.com/?Open\_Source/Distributions](https://w.amazon.com/bin/view/Open_Source/Hello/)
 |
 |
| If AWS-provided code _includes_ any third-party code, are all required attributions are present? For example the [CC-BY license](https://creativecommons.org/licenses/by/4.0/) allows usage, but requires attribution and indications of any changes. |
 |
| If the workshop uses or references third-party data sets, does AWS have the right to use those data sets in a workshop scenario? If you&#39;re unsure, flag this and ask Legal via [https://legal.amazon.com/sites/AWS-Collab/agreementresources/Sherpa/SitePages/Home.aspx](https://legal.amazon.com/sites/AWS-Collab/agreementresources/Sherpa/SitePages/Home.aspx) |
 |
| If the workshop references AWS-owned sample code on Github, is the code under an Amazon-owned Github Organization, for example AWS-samples?
- Personally-owned github repos are not acceptable.
- For AWS sample code, there&#39;s an [expedited process](https://w.amazon.com/?Open_Source/Open_Sourcing#publish-sample-code) to review and release sample code
 |
 |

### Content, spelling, and grammar

|
 | **Yes/No/Comments** |
| --- | --- |
| Is the information in the workshop factually correct? |
 |
| Could you complete all the steps in the workshop without error? |
 |
| If you did encounter errors, did the workshop guide help resolve those? |
 |
| Is the workshop specific enough in its instructions, without being verbose?
- This can be dependent on level. For example, a 100-level workshop may need to walk a customer through all steps of launching an EC2 instance. A 400 level workshop may simply tell a user to launch an EC2 instance using an AmazonLinux2 AMI.
- Note/list any sections that could be improved.
 |
 |
| Are there any sections that would be better described with a diagram or image?
- Minimize the use of AWS Console screenshots. Frequent changes to the AWS Console mean these become outdated, and then cause confusion.
 |
 |
| Does the workshop avoid rhetorical devices that may be unclear to non-native-language speakers? For example &quot;grab a cup of joe while you wait. Most of the time, it&#39;s faster than a rat up a drainpipe&quot; |
 |

### Accessibility and Inclusion

|
 | **Yes/No/Comments** |
| --- | --- |
| Do all images have accurate, descriptive alternate text?
- The IMG Hugo shortcode allows alternate text to be included.
 |
 |
| Do images avoid red/green elements that could cause issues for people with colorblindness? |
 |
| Do videos have (or allow for) subtitles? |
 |
| Does the workshop content adhere to Amazon&#39;s [Inclusive Tech Guidelines](https://w.amazon.com/bin/view/EE/Programs/Inclusive_Tech/Guidelines)?
- e.g.: Do not use terms such as blacklist/whitelist, master/slave, etc.
 |
 |

### Internationalization / multi-language

|
 | **Yes/No/Comments** |
| --- | --- |
| Are all languages/translations listed in the drop-down on the left-hand menu? Do all language choices link to complete translations of the workshop?
- The Aws-workshop-template ships with English and French as defaults, to show how multi-language works. Sometimes workshop owners leave the French default pages in place.
 |
 |

### Additional comments

_Space for any additional comments you may have for the workshop author._