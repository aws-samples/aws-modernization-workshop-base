---
title: "SOlace-S3 connector setup"
chapter: true
weight: 1 
---

## Introduction
In this section we will be linking the S3 bucket with the Solace event mesh using the Solace-S3 native connector.

### Setting up the connector

#### Step 1 - Select service
- Navigate to the cloud console and login to the PubSub+ broker manager using the link in the top right corner
![S3 - Link PubSub+ broker manager - Allow Access](/images/moduleOne/broker_console.png)
- Click on the **Connectors** link on the left menu and click on **Create a new connector**
- Select the AWS logo --> the AWS S3 bucket and click **Authenticate**

#### Step 2 - Authenticate
- Fill in the following details in the first step and click **Connector setup**
  - Connector name : Put in a name of your choice
  - Access key id : Put in the **Access key** that you created from the IAM console.
  - Access key : Put in the **Secret Access key** that you created from the IAM console.
  - Bucket name : Name of the bucket that you created
  - Bucket region : The region of the bucket where you created. In our case, it was `ap-northeast-1` \
Below is a screenshot of the step for your reference
![S3 - Create-connector-step-2](/images/moduleFour/S3-connector-step-2.png)

#### Step 3 - Connector setup
- Proceed with the retrieved value in the **Connector Setup** as below
  ![S3 - Create-connector-step-3](/images/moduleFour/S3-connector-step-3.png)

#### Step 4 - Subscription setup
In this step, we define the folder structure where the events will be persisted. \
We use Substitution Expressions which are a Solace-specific expression language used to replace specific text attributes (request targets, request headers, etc.) with system generated output.
You can read more about them over here : [Substitution Expressions](https://docs.solace.com/Messaging/Substitution-Expressions-Overview.htm)
- Use the following values for the subscription setup :
    - File name mapping function : `/quote-engine/APAC-Region/${localYear()}/${localMonth()}/${localDay()}/${localHour()}/${topic(3)}/${topic(4)}`
    - Subscriptions : `TW/TWSE/LIVE/*`
- Click on **Create and Enable Connector**

#### Step 5 - Summary
This step details the results of the asset creation result and its operational state
![S3 - Create-connector-step-5](/images/moduleFour/S3-connector-step-5.png)


As the events are produced on the **Remote - On premise** broker and is pushed thru to the mesh, they will be saved to the S3 bucket as files in the folder structure we defined.
