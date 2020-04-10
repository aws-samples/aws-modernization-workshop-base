+++
title = "Intstrumentation"
date = 2019-09-09T17:42:10+01:00
weight = 10
+++

### 1. Instrumenting your Lambda Function

1. In the AWS Console, Find the [New Relic layer](https://nr-layers.iopipe.com/) that matches your runtime and region. We will be using the **NewRelicNodeJS12X** layer for this workshop.
1. Copy the Amazon Resource Name (ARN) of the most recent version and add it in the AWS Lambda console for your function.
1. Update your functions handler to point to the newly attached layer in the console for your function:
  * *newrelic-lambda-wrapper.handler*
1. Add these environment variables to your Lambda console:
  * *NEW_RELIC_ACCOUNT_ID*: Your New Relic account ID
  * *NEW_RELIC_LAMBDA_HANDLER*: Path to your initial handler. (*index.handler*)

### 2. Stream CloudWatch logs to New Relic Lambda

Previously in this workshop, you set up a *newrelic-log-ingestion* Lambda function. Now that you've also instrumented your Lambda function, you must link that function's CloudWatch Logs stream to the *newrelic-log-ingestion* Lambda. To do this:

1. Open CloudWatch and select **Logs** in the left-hand menu, and then select the log group for the function you are monitoring.
1. Select **Actions** and choose **Stream to AWS Lambda**.
1. Under **Lambda function**, select the *newrelic-log-ingestion* function.
1. Set the **Log format** to *JSON*.
1. Click the **Next** button.
1. Click **Start streaming**.
