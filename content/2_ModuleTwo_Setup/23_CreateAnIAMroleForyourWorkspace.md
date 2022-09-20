---
title: "Create an IAM Role for your workspace" # MODIFY THIS TITLE
chapter: true
weight: 3 # MODIFY THIS VALUE TO REFLECT THE ORDERING OF THE MODULES
---

<!-- MORE SUBMODULES CAN BE ADDED TO DIVIDE UP THE SETUP INTO SMALLER SECTIONS -->
<!-- COPY AND PASTE THIS SUBMODULE FILE, RENAME, AND CHANGE THE CONTENTS AS NECESSARY -->

# Create an IAM Role for your workspace <!-- MODIFY THIS SUBHEADING -->

## Submodule Three Heading <!-- MODIFY THIS SUBHEADING -->

This paragraph block can be used to explain how to create a workspace if necessary. Example content guidance can be found at the bottom of the page.

{{% notice info %}}
<p style='text-align: left;'>
**REMOVE:** With the exception of _index.md, the module folders and filenames should be changed to better reflect their content, i.e. 1_Planning as the folder and 11_HowToBegin as the first submodule. Changing the "weight" value of the header is ultimately what reflects the order the modules are presented.
</p>
{{% /notice %}}

### Next Section Heading <!-- MODIFY THIS HEADING -->
This paragraph block can optionally be utilized to lead into the next section of the workshop.

#### Example Content Guidance

### Create an IAM Role for your workspace <!-- MODIFY THIS SUBHEADING -->

Info: Starting from here, when you see command to be entered such as below, you will enter these commands into Cloud9 IDE. You can use the Copy to clipboard feature (right hand upper corner) to simply copy and paste into Cloud9. In order to paste, you can use Ctrl + V for Windows or Command + V for Mac.

    Follow this deep link to create an IAM role with Administrator access.
    Confirm that AWS service and EC2 are selected, then click Next to view permissions.
    Confirm that AdministratorAccess is checked, then click Next to review.
    Enter CircleCI-Workshop-Admin for the Name, and select Create Role createrole
