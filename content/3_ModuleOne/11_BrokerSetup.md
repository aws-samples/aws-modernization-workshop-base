---
title: "Solace Event broker setup" 
chapter: true
weight: 1
---

## Setup the Solace PubSub+ broker instance
Once you are logged in to the Solace cloud portal with the details you registered with , you should see something like this:
![Solace Portal Mission Control](/images/moduleOne/mission-control.png)

Click on "Cluster Manager" to go into where you create and manage your broker services. 
Then click the big "+" Plus button to create a new Service. 
Ensure you have selected Developer Service, Amazon Web Services as the cloud service provider, 
and then click the map to find a region close to you:

![Create Service](/images/moduleOne/broker_create_service.png)

Give your Solace PubSub+ Cloud service instance a name, and then tell it to start! 
Under the covers, a Solace event broker will be deployed and configured in the cloud you indicated, ports configured, load-balancer setup, monitoring enabled, etc. 
It takes about 5 minutes, and then you'll be ready!

> It is safe to navigate away from the "Solace is starting" page while the broker is being deployed in the cloud.  Feel free to explore the rest of Solace Mission Control, including the Event Portal!

Once the Solace broker is up and running, click on the broker name and enter it.

### Solace PubSub+ Cloud

Once your service is deployed and ready, simply click on it to go into it and look at some basic configuration information:
![Broker Console](/images/moduleOne/broker_console.png)

Notice some buttons across the top:

* The "Connect" tab shows you all the required connection information for your messaging pub/sub applications (e.g. host, username, password, etc.), which we'll need in later steps. The info can be grouped either by protocol or by programming language.
* At the top-right, there should be a button saying "Open PubSub+ Broker Manager". Click on that to go into the Manager GUI.

### PubSub+ Manager

From this webapp, you'll be able to view configured and runtime information, create new queues, create usernames and profiles, and other various administrative tasks for the Solace broker.
![PubSub+ Manager](/images/moduleOne/pubsubManager.png)

On the left side of the screen are the main sections to navigate through:

* **Message VPN**: VPN-level stats and config (a Message VPN is a virtual partition of a single broker... one Solace broker can host multiple Message VPNs, and each VPN can have different authorization schemes and topic spaces; client/messaging application activity happens within the scope of a VPN)
* **Clients**: information about connected and configured client applications
* **Queues**: used for Guaranteed / persistent messaging
* **Connectors**: helpful wizards to connect to a variety of web services
* **Access Control**: where you create new client usernames, ACL profiles, and client profiles
* **Replay**: where you can enable replay, to allow the broker to send previous messages again
