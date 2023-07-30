---
title: "Eventbridge Scheduler setup"
chapter: true
weight: 1 
---

## Introduction
In this section, we will be setting up an eventbridge scheduler which will trigger the lambda function that was created in the previous step.

### Defining an eventbridge scheduler
- On the definition page of the lambda function that you have recently created, there is a section where you can add a new trigger as below
  ![Lambda-trigger](/images/moduleThree/lambda-triggers.png)
- Click on Add trigger
- In the trigger configuration :
  - Choose **EventBridge (CloudWatch events)** as the source
  - Create a **new** rule
  - Name : `tokyo-summary-event-lambda-schedule`
  - Description : Enter a description
  - Rule Type : Schedule expression
  - Schedule expression : `rate(5 minutes)`
  
Below is a screenshot of the configuration for your reference
  ![Lambda-trigger-configuration](/images/moduleThree/lambda-trigger-config.png)

### Testing
Based on the rate specified, the trigger will execute the lambda every 5 minutes. \
You can verify the triggering of the lambda via the monitoring tab in the lambda.