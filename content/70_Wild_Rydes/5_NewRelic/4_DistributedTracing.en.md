+++
title = "Troubleshooting: Distributed Tracing"
date = 2019-09-09T17:42:10+01:00
weight = 40
+++

In addition to providing performance data for your Lambda functions, New Relic Monitoring for AWS Lambda also enhances your ability to troubleshoot issues.

Let's now click on **Distributed tracing**. (underneath the CloudWatch metrics link you clicked on in the previous module) The **Distributed tracing** page displays all the traces for a particular function:

![Distributed Tracing](/images/wildrydes/distributed-tracing.png)

Click on one of the **Root Entry Spans** (highlighted in blue above) to drill down into a single instantation of your Lambda function, and then click on the **Expand all** link:  

![Distributed Tracing Details](/images/wildrydes/trace-details.png)

We can see here that RequestUnicorn is a simple Lambda function consisting of 3 spans.  Spans represent the time spent in a service or a service function. The span count includes both in-process and cross-process spans, but in-process spans are collpased by default.

Clicking on an individual span, **DynamoDB putItem** in this case, provides performance data for that particular span. Distributed tracing is extremely valuable in diagnosing exactly where in your services and/or services function performance-related issues are taking place:

![Span Details](/images/wildrydes/span-details.png)
