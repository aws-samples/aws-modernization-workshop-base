+++
title = "Configure New Relic's log-ingestion Lambda"
date = 2019-10-03T10:54:25-07:00
weight = 4
+++

{{% notice note %}}
Please ensure you perform these actions for us-west-2 as they are region specific.
{{% /notice %}}

To configure the New Relic Lambda, go to the [AWS Serverless Application Repository](https://aws.amazon.com/serverless/serverlessrepo/), which is where our *newrelic-log-ingestion* Lambda is stored. This repo is a collection of serverless applications published by developers, companies, and partners in the serverless community. It allows developers to share their Lambda functions code with customers, who can then find and deploy the corresponding application Lambda function. Each application is packaged with an AWS Serverless Application Model  (SAM) template that defines the AWS resources used.

To configure the New Relic Lambda with the AWS Serverless Application Repository:

1. From the AWS console, go to the Lambda section, select **Create function**, and select **Serverless Application Repository**.
1. Search for *newrelic* and find the *newrelic-log-ingestion* Lambda. Follow the instructions in the [Lambda's documentation](https://serverlessrepo.aws.amazon.com/applications/arn:aws:serverlessrepo:us-east-1:463657938898:applications~NewRelic-log-ingestion) to deploy it. A SAM template will build the Lambda.
1. In the environment variable section  in AWS console, set the *LICENSE_KEY* environment variable to your New Relic license key. Note: If you have multiple accounts or a master-subaccount hierarchy, ensure that the license key used corresponds to the same account connected to AWS.
1. Set the *LOGGING_ENABLED* environment variable to *true*.
