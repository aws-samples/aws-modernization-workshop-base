---
title: "3. AWS Event bridge scheduler triggering AWS Lambda" 
chapter: true
weight: 3
---
## Introduction

In this section we will be talking about the flexibility of producing events to a Solace Event mesh using an AWS Lambda. \
To make things more interesting, we will be using an Eventbridge scheduler to trigger this Lambda function every 5 minutes. \
This event will be published across the event mesh and consumed by a consumer running on the _on-premise_ infrastructure of the enterprise landscape to further demonstrate the power and flexibility of the Solace Event mesh. 

After this module you will have :
- Setup an AWS Lambda function which publishes an event to the PubSub+ event broker that you have created.
- Trigger this lambda function using Event bridge scheduler
