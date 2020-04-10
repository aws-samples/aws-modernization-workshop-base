+++
title = "Overview"
date = 2019-09-09T17:42:10+01:00
weight = 1
+++

New Relic monitoring for AWS Lambda offers in-depth performance monitoring for your Lambda functions. In this module you'll learn how to instrument a Lambda function for Observability.

## Architecture Overview

Before going through the implementation procedures, it may help you to understand how data flows from your Lambda functions to New Relic:

![New Relic Monitoring for AWS Lambda architecture](/images/wildrydes/new-relic-lambda-monitoring-architecture.png)

When New Relic's Lambda monitoring is enabled, this is how data moves from your Lambda function to New Relic:

1. **The Lambda function** is instrumented with our code. When the Lambda is invoked, log data is sent to CloudWatch.
1. **CloudWatch** collects Lambda log data and sends it to our log-ingestion Lambda.
1. The **log-ingestion** Lambda sends that data to New Relic.

## Implementation Instructions

:heavy_exclamation_mark: Ensure you've completed the [RESTful APIs][restful-apis] step before beginning

Each of the following sections provides an implementation overview and detailed, step-by-step instructions. 

[restful-apis]: ../4_restfulapis.html
