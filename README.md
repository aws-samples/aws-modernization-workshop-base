

# AWSWorkshop.io base workshop 

Clone this branch if your workshop is part of the [AWS Marketplace DevOps Workshop Series](https://pages.awscloud.com/awsmp-h2-dev-aws-marketplace-devops-workshop-series.html). This is a base skeleton template for the Marketplace flow and there are several key changes from the standard workshop-base. 

In an effort to create the best possible customer experience, the template is using Hugo Theme Learn's [Multi-Language support](https://learn.netlify.app/en/cont/i18n/) to act as a track or flow controller. This will create two complete separate tracks for the customers to use with the default track being the self-guided or on your own style workshop. Customers will be able to select the track on a drop down on the left hand side of the workshop nav bar. The self-guided workshop track will be the default. 

The AWS hosted or Event Engine track will be through the usage of filename.ee.md. If the flow has the same common file as the default flow, use a link ```ln -s filename.md filename.ee.md```. Using this method any changes to one file will be reflected in the other. If your development system does not support links, it's ok to create a copy of the file and name it filename.ee.md.

## Quick start, minimum changes:
To get started you will need the following information. If you don't have this info, please reach out to your AWS PSA. 
- Seller badge (image)
- Available in MP link
- Credit request link
- CSAT form URL

1. /_index.md - Change the href url to **Available in MP Link** and the png image to **Seller badge (image)**. Be sure to put the png file you receive into the folder /static/
2. /030_self_guided_setup/request_credit.md - Change ```https://pages.awscloud.com/awsmp-wsm-dev-workshop-series-credit-request.html?trk=lab_{partnerName}``` to the provided **Credit request link**. On the same page change ```https://aws.amazon.com/marketplace/pp/B07PZY3369?&trk=el_a134p000003yrYeAAI&trkCampaign=AWSMP_pdp_dev_x_dg&sc_channel=el&sc_campaign=el_awsmp_mult&sc_outcome=Marketplace``` to the Available in MP link.
3. /099_survey/_index.md - Change ```https://pages.awscloud.com/awsmp-wsm-dev-workshop-series-csat-lab-completion.html``` to the ***CSAT form URL**. 

> Note: this is just a minimum of the changes necessary to make the base template specific to your workshop content. You will still need to review every page, including the ones listed above for content specific to your workshop and company. **When complete or near complete, use the dev-review.md doc in /review to validate you are ready for publishing**
## Create an additional flow/track/path
To create an additional flow for your workshop to accommodate other AWS events you will need to replicate every file in /content so that Hugo will pick these up as part of a new language. We have pre-created flows in config.toml file for default and for EE (Event Engine). To create a flow for EE copy or link ```ln -s``` each file you want as part of that flow. Example 010_introduction/_index.md gets copied or linked to 010_introduction/_index.ee.md. ***Note*** there is no common files that show up in the EE flow. If you want a page to be available in a different flow there must be a file with ee.md extension, otherwise Hugo will not pick this file up.

It is recommended to create the default flow first, then create the second flow after you have ensure the first flow works as expected.

If you are interested in creating additional flows, please see Hugo's [Multi-Language support](https://learn.netlify.app/en/cont/i18n/). The example uses Languages such as English, but we have repurposed this for supporting different flows.

> ***Why did we create flows?*** Creating flows helps improve the user experience by presenting users with only the information they need. Without flows, you would provide users with decision points that they would have to navigate correctly, such as "Are you at an AWS Event? Click Here, or Are you doing this Event on your own? Click Here". This can get very confusing to users, so the usage of flows cuts down on this decision tree mess and makes for a much better user experience.
## Additional instructions: integrating with your workshop
At this point, you either just started to create a workshop, **OR** the workshop content is already live, and these changes must be integrated in.

If you are just starting to create a workshop:
1. Update the first 3 sections: introduction, EE setup, self-guided setup
   * Have the Partner fill out the introduction, problem statement etc.
   * If there are additional setup instructions, feel free to change the filename and other contents in the page accordingly
1. Update all relevant information in the 3 sections, i.e. update roleName and other partner-specific language
1. Set up a 040_partner_setup directory, replacing partner with the actual partner's name

These next instructions are for workshops that are already created:
1. Update config.toml with the relevant changes
1. Copy and paste the custom-header.html file over
1. Copy and paste the mp-devops-series.css file over

The following instructions are for both newly created and completed workshops:
1. Update the Marketplace badge (static/images/setup/available-in-awsmp-badge.png) to the partner specific badge.
   * Also update the link to the actual partner's Marketplace listing
1. Update the link in the request credit button to the proper partner tracking link
1. Symlink all the common content to fileName.ee.md
   * Common content are partner lab instructions
   * Follow the same pattern in the Introduction section files
   * Symlink allows any changes to the original file to have the same changes made to the linked target file (*.ee.md)


## Changes from base branch
1. Introduction Section
   * This
1. Event Engine Setup Section
1. Self Guided Setup Section
1. Your Workshop Content
1. Cleanup Section
1. Survey

This branch also contains the following static resources and scripts:
1. static/images/available-in-awsmp-badge.png
   * You should receive a specific Partner Marketplace Badge image. If not, reach out to ajonsso@.
2. static/css/mp-devops-series.css
   * This includes the CSS for the buttons on the AWS Request Credit Page.
3. layouts/partials/custom-header.html
    * This injects both Marketo data tracking script to the head of every page in the workshop and inserting the various CSS files.

config.toml changes:
1. defaultContentLanguage = "oyo".
   * "oyo" is short for on-your-own.
1. Setting defaultContentLanguageInSubdir to "false".
   * This allows *.awsworkshops.io/ to default to the oyo lab.
1. Setting disableLanguageSwitchingButton to false.
   * This allows the ability to toggle between EE and oyo track in the navigation button
1. Setting the languages parameters on L:82