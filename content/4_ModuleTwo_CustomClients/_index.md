---
title: "2. Setup custom clients for events"
chapter: true
weight: 3
---

## Introduction

In this section, we will be talking about using Cloud9 backed AWS EC2 instances to set up and deploy custom applications. \
These application connect to the Solace PubSub+ broker that you have created and consume market data events that are published on the **Remote** broker.

After this module you will have :
- Connected to an EC2 instance via Cloud9
- Setup Java, NodeJs, Git, Maven, Docker and Docker Compose
- Checked out and built 2 custom applications :
  - Java, Spring boot based administration application
  - NodeJs, Angular based front end application
- Understand Solace PubSub+ broker capabilities like _Direct Messaging_, _Eliding_, _SEMP API_ etc
- Visualize the market data events by consuming them over the event mesh