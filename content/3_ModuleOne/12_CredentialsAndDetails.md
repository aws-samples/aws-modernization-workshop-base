---
title: "Gathering credentials and connection details" 
chapter: true
weight: 2 
---

## Credentials and required connection details.

For this workshop, we will require multiple sets of credentials for connecting to different brokers and services. 
This section describes and details all the credentials that are required.

Below are the information details that are required for this workshop:

1. The Solace Element Management Protocol (SEMP) hostname and credentials of the central "on-premise" broker which we will call as **Remote**.
The SEMP API is used for configuration activities and its details are listed below: 
>   Host url: `mr-connection-3d78t9gmhxv.messaging.solace.cloud:943` \
    Username: `solace-aws-int-onprem-admin` \
    Password: `ljcifmsim0ad3oek7dd70q3cb3`

2. The hostname and credentials of the **Remote** broker. Its details are listed below:
>   Host url: `mr-connection-3d78t9gmhxv.messaging.solace.cloud:55443` \
    Username: `solace-cloud-client` \
    Password: `fpmjrcl38m8r5iqcvg753udgk7`

3. The hostname and credentials of the newly created broker which we will call as **Initiator**.
 The easiest way to grab this is from the Connect tab of the cloud console
![Broker Console - Connect](/images/moduleOne/brokerconsole_connect.png)

This tab lists the credentials and protocol specific host urls that must be used while connecting to the Solace broker using a supported client library. \
We need two set of connection details as below : \
    a. Credentials for using in the Spring Java application \
    Navigate to the screen below as shown
![Console-Connect - Java Spring](/images/moduleOne/brokerconsole_connect_creds_java.png)
Make a note of the following properties in a separate file as they will be required for the following steps:
- Public Endpoint
- Username
- Password
- Message VPN
![Console-Connect - Creds highlighted](/images/moduleOne/brokerconsole_connect_creds_java_highlighted.png) 

  b. Credentials for using in the Angular frontend application \
  Navigate to the screen below as shown
  ![Console-Connect - Nodejs](/images/moduleOne/brokerconsole_connect_creds_nodejs.png)
  Make a note of the following properties in a separate file as they will be required for the following steps:
- Public Endpoint
- Username
- Password
- Message VPN
  ![Console-Connect - Creds highlighted](/images/moduleOne/brokerconsole_connect_creds_nodejs_highlighted.png)

4. The SEMP hostname and credentials of the **Initiator** broker
These credentials can be found in the _Manage_ tab of the cloud console as show below
![Console-Connect - SEMP creds highlighted](/images/moduleOne/brokerconsole_manage_creds_semp_highlighted.png)
Make a note of the following properties in a seperate file as they will be required for the forthcoming steps:
- Public Internet URL
- Message VPN Name
- Username
- Password

5. An API token for the Solace Cloud REST APIs

Follow the steps detailed in the link over here : [Creating an API Token](https://docs.solace.com/Cloud/ght_api_tokens.htm#Create)
Make sure that you enable the following permissions during the process :
    - **Organization Services - both read and write** \
**Keep this token safe as it will not be available again**

6. The service id of the **Initiator** broker service that you have created.
    The easiest way to grab this is from the url on the service details screen as below :
![Service details - ServiceId highlighted](/images/moduleOne/service_details.png) 
The id is the alphanumeric value that comes after the _services/_