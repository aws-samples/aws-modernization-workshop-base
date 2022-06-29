---
title: "Partner Setup Instructions" # MODIFY THIS TITLE
chapter: true
weight: 1 # MODIFY THIS VALUE TO REFLECT THE ORDERING OF THE MODULES
---

# Partner Setup Instructions <!-- MODIFY THIS HEADING -->

## Submodule One Heading <!-- MODIFY THIS SUBHEADING -->

This paragraph block should be an introduction to the submodule.

### Submodule One Subheading <!-- MODIFY THIS SUBHEADING -->
This paragraph block should be utilized to start the submodule. <br>

{{% notice info %}}
<p style='text-align: left;'>
**REMOVE:** With the exception of _index.md, the module folders and filenames should be changed to better reflect their content, i.e. 1_Planning as the folder and 11_HowToBegin as the first submodule. Changing the "weight" value of the header is ultimately what reflects the order the modules are presented.
</p>
{{% /notice %}}

### Next Section OR Conclusion Heading <!-- MODIFY THIS HEADING -->
This paragraph block can be utilized to lead into the next section of the workshop (which might be a conclusion) or be a conclusion itself.

#### Example Guidance Content Below


# Do you require attendees to sign up for things? <!-- MODIFY THIS HEADING -->


### Introduction <!-- MODIFY THIS HEADING -->
In this section, we are going to discuss tasks and concepts like retrieving access tokens and other configurations within some integration services.


### Docker Hub <!-- MODIFY THIS HEADING -->

Docker Hub is a service provided by Docker for finding and sharing container images with your team. It is the world’s largest repository of container images with an array of content sources including container community developers, open source projects and independent software vendors (ISV) building and distributing their code in containers.


### Create a Docker Hub Access Token <!-- MODIFY THIS HEADING -->

The pipeline will package the application into a Docker image. It then pushes that image a public Docker Hub image repository so that it will be available to the deployment segment of the pipeline. To push or upload the newly-built Docker image, the pipeline will need an access token to authorize transaction on your Docker Hub account. You will need to create a new access token (https://docs.docker.com/docker-hub/access-tokens/) and store it for use in later modules. To create your new access tokens:

    Log in to hub.docker.com
    Click your username in the top right corner and select Account Settings
    Select Security > New Access Token.
    Add a description for your token that indicates where the token will be used, or that sets a purpose for the token
    Copy the token that appears on the screen and record it in a safe location for use in future modules. Make sure you do this now! Once you close this prompt, Docker will never show the token again and you will have to create a new one

Warning: Docker Hub credentials and access tokens must be protected and not shared with unauthorized parties to prevent exposure and unauthorized access.

Now that you have created and safely recorded your new access token, let’s move to the next section and create a new Snyk Access token.

### Snyk <!-- MODIFY THIS HEADING -->
Snyk is an open source security platform designed to help software-driven businesses enhance developer security. Snyk’s dependency scanner makes it the only solution that seamlessly and proactively finds, prioritizes, and fixes vulnerabilities and license violations in open source dependencies and container images.

### Create Snyk Access Token <!-- MODIFY THIS HEADING -->

    Visit your Snyk account (Account Settings > API Token section) (https://app.snyk.io/account)
    In the KEY field, select click to show, then select and copy your API token from the field
    Paste the token that appears on the screen in a safe location for use in future modules

Warning: Your Snyk access token must be protected and not shared with unauthorized parties to prevent exposure and unauthorized access.

You can read more about Snyk Access Token from their docs here.

Great, you have created and safely stored your newly created Snyk access token, Now, let’s create the Terraform Cloud access token.


### Terraform Cloud <!-- MODIFY THIS HEADING -->

Terraform Cloud is an application that helps teams use Terraform together. It manages Terraform runs in a consistent and reliable environment, and includes easy access to shared state and secret data, access controls for approving changes to infrastructure, a private registry for sharing Terraform modules, detailed policy controls for governing the contents of Terraform configurations, and more.

You will be using Terraform Cloud to store the Terraform state of the infrastructures your pipeline will provision and deploy using Terraform in future modules.

### Create Terraform Cloud Access Token <!-- MODIFY THIS HEADING -->

    Create a `[Terraform Cloud ](https://app.terraform.io/signup/account)` account
    Create a new '[Terraform Cloud organization ] (https://learn.hashicorp.com/terraform/cloud-getting-started/signup#create-your-organization)'
    Create a new '[Terraform Cloud workspace ] (https://learn.hashicorp.com/terraform/cloud-getting-started/create-workspace)' named: arm-aws-ecs
    Click the CLI-driven workflow option
    In the workspace, click arm-aws-ecs > Settings > General then enable '[local execution mode] (https://www.terraform.io/docs/cloud/workspaces/settings.html#execution-mode)'
    Go to the '[User Settings section] (https://www.terraform.io/docs/cloud/users-teams-organizations/users.html#user-settings)' in the Terraform Cloud Dashboard
    In the User Settings section, Create a new '[Terraform API token] (https://www.terraform.io/docs/cloud/users-teams-organizations/users.html#api-tokens)' then copy and paste the token in a secure location for later use.

Warning: Your Terraform Cloud API token must be protected and not shared with unauthorized parties to prevent exposure and unauthorized access.

Great, you have created and safely stored your newly created Terraform Cloud API Token.