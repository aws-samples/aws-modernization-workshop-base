---
title: "AWS Lambda setup"
chapter: true
weight: 1 
---

## Introduction
In this section, we will be setting up an AWS Lambda function using a Java artifact.


### Defining a lambda function with the console
- Open the [Functions page](https://console.aws.amazon.com/lambda/home#/functions) of the Lambda console.
- Choose **Create function**
- Select **Author from scratch**
- Enter the name as : _tokyo-summary-event-generator_ and the Runtime as _Java 11_
- Click on **Create function**
Below is a screenshot which demonstrates the steps
![Lambda-create-function](/images/moduleThree/lambda-create-function.png)

### Updating the code source
- The code source or executable for this lambda has been provided in the Github repository that was made available at the beginning of this session.
- Within the folder **solace-aws-integration/lambda_function**, there is a jar file named : **apac-summary-event-generator-1.1.1.jar**
- Click on the _Upload from_ button, choose .zip or .jar file and select the above jar file
- Click save

### Defining the runtime settings
Once your new lambda function is created, you need to setup the runtime settings.
- Scroll down to the **Runtime settings** and click on _edit_
- In the handler, put in the value : `com.solace.quoteengine.lambda.summaryeventgen.handlers.SummaryEventGenerator::handleRequest`
- Click **save**
Below is a screenshot which demonstrates the steps
![Lambda-Edit runtime settings](/images/moduleThree/lambda-edit-runtime-settings.png)

### Defining the environment variables
You will also need some environment variables for your lambda function to be able to connect to your newly created broker and post events to the topic.
- Navigate on the **Configuration** tab and click on edit
  ![Lambda-Edit configuration](/images/moduleThree/lambda-edit-config-vars.png)
- Click on the button **Add environment variable** and add in the below 5 variables.
  - SOLACE_HOST_URL : The public endpoint specific for Java-Spring applications which was captured in step 3.a of module 1
  - SOLACE_VPN : The message vpn which was captured in step 3.a of module 1
  - SOLACE_USERNAME : The username which was captured in step 3.a of module 1
  - SOLACE_PASSWORD : The password which was captured in step 3.a of module 1
  - SUMMARY_EVENT_TOPIC : `trading/quotes/summary/event/v1/published/apac`
    ![Lambda-Setup config vars](/images/moduleThree/lambda-setup-config-vars.png)

### Testing out the lambda function
Once all the cofiguration and setup is complete, the lambda can be tested via the console's **Test** tab
- Click on the _Test_ button as below :
  ![Lambda-Test screen](/images/moduleThree/lambda-test-screen.png)
- As the lambda is executed, you can verify the results by inspecting the details of the test run as below.
![Lambda-Test result](/images/moduleThree/lambda-test-result.png)
As you can see, the lambda logs that its producing an event like below :
```  
Summary Event published:{
  "regionId": "eu-northeast-1",
  "regionName": "Tokyo",
  "timezoneName": "JST",
  "totalEventsProcessed": 2834,
  "totalEventsPending": 853,
  "eventTimeStamp": 1690721293
  }
```
