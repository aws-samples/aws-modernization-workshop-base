---
title: "Event mesh integration" 
chapter: true
weight: 3 
---

## What is the Solace Event mesh

As we said before, the Solace event mesh is a flexible and unified architecture that connects applications, microservices, and distributed components.
Below are some benefits of the Solace event mesh :
- Seamless communication between distributed components, applications, and microservices.
- Scalability to handle growing workloads and a large number of events.
- Reliable event delivery with minimized risk of data loss.
- Flexibility to integrate different systems and technologies.
- Event-driven agility and responsiveness.
- Decoupling of applications and services for easier maintenance.
- Global event distribution across multiple locations.
- Robust security features, including access control and encryption.
- Monitoring and management tools for better insights and issue resolution.
- Future-proof solution aligning with modern application design principles.

As a part of this workshop, we will be linking the broker that you created in the previous step with the central _on-premise_ broker that has already been provisioned and made available to the participants.
This link will be bi-directional static link that allows events and messages to be passed between the two brokers.

Follow the steps below to create this static link :

- Open the PubSub+ Broker Manager by clicking on the top-right button
![Broker Console - Open manager](/images/moduleOne/brokerconsole_openManager.png)

- In the right-side menu, click on the "Bridge" button
![PubSub Manager - Bridge creation](/images/moduleOne/pubsubManager_bridges.png)

- Click on the "Click to Connect" button on the top-right and enter the static bridges creation wizard
![Static Bridges - click to connect](/images/moduleOne/bridges_clickToConnect.png)

- In the section titled _Remote Message VPN Management Credentials_, enter the SEMP hostname and credentials of the **Remote** broker which we defined in the section earlier.
![Click to connect - Remote Message VPN Management Credentials](/images/moduleOne/bridges_clickToConnect_Screen_1.png)
Click on the button _Select Remote Message VPN_

- Select the retrieved remote vpn name as shown below and click on the button _Remote Connection Setup_
![Click to connect - Select Remote message VPN](/images/moduleOne/bridges_clickToConnect_Screen_2.png)

Make sure to fill in the details in this section very carefully as they are used to establish the connection.
1. Remote Message VPN connection
   - Host list : Fill in the hostname of the **Remote** broker, this is detailed in the point#2 of **Credentials and required connection details** section
2. Bridge Client for Remote Message VPN
    - Client Username : Select the value `solace-cloud-client` from the dropdown
    - Password : Fill in the password of the **Remote** broker, this is detailed in the point#2 of **Credentials and required connection details** section
    - Confirm Password : Fill in the same value as above
3. Bridge Client for Local Message VPN
   - Client Username : Select the value `solace-cloud-client` from the dropdown
   - Password : Fill in the password of the **Initiator** broker, this is detailed in the point#3 of **Credentials and required connection details** section
   - Confirm Password : Fill in the same value as above
4. Enable the button _TLS Enabled_
![Click to connect - Remote connection setup](/images/moduleOne/bridges_clickToConnect_Screen_3.png)
Click on the button _Create Bridge and Test Connection_

- If everything is fine, then a success page will be displayed as below.
![Click to connect - Bridge creation](/images/moduleOne/bridges_clickToConnect_Screen_4.png)

- Click on the button _Set up Subscriptions_ where you can specify the topic subscription that you want to attract from the **Remote** broker
  - Specify the topic subscription `TW/TWSE/>`
  - Leave the topic direction as is
  - Select the `Direct` quality of service

![Click to connect - Setup subscriptions](/images/moduleOne/bridges_clickToConnect_Screen_5.png)
Click _Apply_

- The last step is to create a subscription on the **Remote** broker for which we will be using a simple postman collection that has been provided as a part of this demo.
As a part of the prerequisites, you will have installed Postman tool which we will be using for making SEMP API calls to the remote broker. \
- Download the following files and save them to a folder of your preference :
  - [Postman Environment file](/postman_collection/Solace-AWS-Demo-Env.postman_environment.json "download")
  - [Postman Collection file](/postman_collection/Solace-AWS-Demo-Collection.postman_collection.json "download") \
- Import the above two files into Postman app.
- Open the collection and adjust the variable **REMOTE_VPN_QUEUE_NAME** to what will be specific to you. The format of the queue name is:
  **YOUR_LOCAL_BROKER_NAME**_solace-aws-int-onprem_Queue. Replace the name of your broker in the placeholder and set it in the current and initial value of the variable.
![Postman environment](/images/moduleOne/postman_env_screen_1.png)
- Open the Postman collection and run it to execute the request. Make sure to have the proper environment selected in the top-right corner.
  ![Postman Collection_screen 1](/images/moduleOne/postman_collection_screen_1.png)
- Run the collection and view the status of the request in the right column
![Postman Collection_screen 2](/images/moduleOne/postman_collection_screen_2.png)
![Postman Collection_screen 3](/images/moduleOne/postman_collection_screen_3.png)


With these steps you will have configured a full functional bi-directional VPN bridge between your new broker and a central **Remote** broker.
This VPN bridge will allow the governed flow of events between the two brokers subject to the topic subscriptions that you have setup. \
Lets move on the to the next step of the workshop.


