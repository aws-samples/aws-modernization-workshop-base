+++
title = "New Relic Monitoring for AWS Lambda: Summary Page"
date = 2019-09-09T17:42:10+01:00
weight = 20
+++

New Relic One's entity explorer provides access to the performance data from all your monitored applications, services, and hosts - including AWS Lambda Functions.

Let's navigate to the [New Relic One website](http://one.newrelic.com) and click on **Entity Explorer:**

![New Relic One](/images/wildrydes/entity-explorer.png)

In the Entity Search field, enter *Unicorn* and select the **RequestUnicorn** function:

![Entity Search](/images/wildrydes/entity-search.png)

Click on the name of the Lambda function, **RequestUnicorn**:

![Select Entity](/images/wildrydes/function-select.png)

You will be presented with the Lambda **Summary** page that presents a quick view into your fucntion's most important performance data:

![Summary Page](/images/wildrydes/summary-page.jpg)

1. **Invocations**: The total amount of times a function has been run. This includes direct REST API calls through the AWS API Gateway as well as through chained event requests.
1. **Duration**: The total time a function ran.
1. **Error rate**: The percentage of invocations that have resulted in errors.
1. **Invocation source**: The list and frequency of how a function was invoked.
1. **Cold starts**: The number of times that a function was invoked that resulted in a cold start. (If a container hosting a function is not created before the function is invoked—a cold start—the function may seem excessively slow).
1. **Metadata**: A list of metadata describing the function.
1. **Details pane**: A list of open violations and metadata and tags associated with the function.
