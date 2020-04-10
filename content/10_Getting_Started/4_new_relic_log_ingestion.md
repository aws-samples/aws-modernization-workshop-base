+++
title = "Configure New Relic's log-ingestion Lambda"
date = 2019-10-03T10:54:25-07:00
weight = 4
+++

{{% notice note %}}
Please ensure you perform these actions for us-west-2 as they are region specific.
{{% /notice %}}

To configure the New Relic Lambda:

1. From the AWS console, go to the Lambda section, select **Create function**, and select **Serverless Application Repository**.
1. Search for *newrelic* and find the *newrelic-log-ingestion* Lambda by clicking the **Show apps that create custom IAM roles or resource policies** checkbox. If you encounter any issues in the steps below, follow the more detailed instructions in the [Lambda's documentation](https://serverlessrepo.aws.amazon.com/applications/arn:aws:serverlessrepo:us-east-1:463657938898:applications~NewRelic-log-ingestion) to deploy it. A SAM template will build the Lambda.
1. In the environment variable section  in AWS console, set the *LICENSE_KEY* environment variable to your New Relic license key. Note: If you have multiple accounts or a master-subaccount hierarchy, ensure that the license key used corresponds to the same account connected to AWS.
1. Set the *LOGGING_ENABLED* environment variable to *true*.
1. Copy and paste your New Relic License Key in the environment variable field labeled *NRLicenseKey*.
1. Click the **I acknowledge that this app creates custom IAM roles and resource policies** checkbox and then click **Deploy**.
