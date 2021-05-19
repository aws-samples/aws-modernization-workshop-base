

# AWSWorkshop.io base workshop 

Clone this branch if your workshop is part of the [AWS Marketplace DevOps Workshop Series](https://pages.awscloud.com/awsmp-h2-dev-aws-marketplace-devops-workshop-series.html). This is a base skeleton template for the Marketplace flow and there are several key changes from the standard workshop-base. 

In an effort to create the best possible customer experience, the template is using Hugo Theme Learn's [Multi-Language support](https://learn.netlify.app/en/cont/i18n/) to act as a track or flow controller. This will create two complete separate tracks for the customers to use with the default track being the self-guided or on your own style workshop. 

The self-guided workshop track will be the default. The AWS hosted or Event Engine track will be through this path: *.awsworkshops.io/ee

Below are the overview of additional/reformatted content as well as instructions on how to integrate this flow into your workshop.


## Overview of Changes
Please read through and familiarize yourself with each markdown, CSS, image, JS files, and the purpose behind each. Additional guidance are written in the files themselves. 

This branch has the following sections:
1. Introduction Section
   * This
1. Event Engine Setup Section
1. Self Guided Setup Section

This branch also contains the following static resources and scripts:
1. static/images/available-in-awsmp-badge.png
   * You should receive a specific Partner Marketplace Badge image. If not, reach out to ajonsso@.
1. static/css/mp-devops-series.css
   * This includes the CSS for the buttons on the AWS Request Credit Page.
1. layouts/partials/custom-header.html
    * This injects both Marketo data tracking script to the head of every page in the workshop and inserting the various CSS files.

config.toml changes:
1. defaultContentLanguage = "oyo".
   * "oyo" is short for on-your-own.
1. Setting defaultContentLanguageInSubdir to "false".
   * This allows *.awsworkshops.io/ to default to the oyo lab.
1. Setting disableLanguageSwitchingButton to false.
   * This allows the ability to toggle between EE and oyo track in the navigation button
1. Setting the languages parameters on L:82

## Instruction on integrating with your workshop
At this point, you either just started to create a workshop with a partner, **OR** the workshop content is already live, and these changes must be integrated in.

If you are just starting to create a workshop with the partner:
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


