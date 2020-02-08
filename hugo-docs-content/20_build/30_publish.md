+++
title = "Publish"
chapter = false
weight = 30
+++

## Publish

Now that your workshop is ready, reach out to your PSA or SA and have them follow the process for getting your workshop published.

#### High level steps

1. The SA will review your submission and makes sure everything works.  
2. The SA will request a repo under aws-samples with the naming standard aws-modernization-workshop-with-{companyname}
3. Once the repo is created, you will fork this repo, copy the content of your workshop to this repo, then issue a pull request.
4. The pull request will be reviewed and merged to master.
5. A CloudFront distribution and deployment pipeline will be setup to deploy the site to an AWS account.
6. Site is now published.

{{% notice note %}}
Because the site has a ci/cd pipeline any future changes only requires a pull request and once approved will automatically publish the changes.
{{% /notice %}}



