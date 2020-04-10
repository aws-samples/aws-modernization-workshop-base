+++
title = "New Relic Monitoring for AWS Lambda: Metrics Page"
date = 2019-09-09T17:42:10+01:00
weight = 30
+++

Now, let's click on **CloudWatch metrics**:

![CloudWatch metrics](/images/wildrydes/cloudwatch-metrics.png)

The **Metrics** page displays AWS Lambda data collected from CloudWatch:

![Metrics Page](/images/wildrydes/metrics-page.jpg)

1. **Invocations**: The total amount of times a function has been run. This includes direct REST API calls through AWS API Gateway, as well as through chained event requests.
1. **Duration**: The total time a function ran.
1. **Throttles**: The number of times a function has been throttled after hitting the service-defined limit for concurrent executions in an AWS account.
1. **Errors**: The number of times an invocation has resulted in an error.
1. **Dead letter errors**: The number of times a function was invoked via a queue, was unable to successfully run, and was left as an unfulfilled invocation request.
1. **Iterator age**: Emitted for stream-based invocations—functions triggered by an Amazon DynamoDB stream or Amazon Kinesis stream—this measures the age of the last record for each batch of records processed. Age is calculated as the difference between the time AWS Lambda received the batch and the time the last record in the batch was written to the stream.
1. **Concurrent executions**: Measures the sum of concurrent executions for a function at a given point in time for that specific function.
