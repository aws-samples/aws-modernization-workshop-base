---
title: "Introduction"
chapter: true
weight: 1
---

# Introduction

In today's fast-paced digital landscape, businesses are constantly seeking innovative ways to handle real-time data processing, seamless integration, and responsive communication between systems. 
Event-Driven Architecture provides a powerful solution to meet these demands by enabling asynchronous, event-based communication and processing.

This workshop will introduce you to Solace, a leading messaging platform designed to simplify event-driven architectures. 
Solace acts as a central nervous system for your data, facilitating the smooth flow of events across diverse systems and applications. 
By leveraging Solace's capabilities, you can build scalable, loosely-coupled, and highly responsive systems.

## Learning Objectives 

As a part of this workshop, you will be implementing EDA in a new expansion region for a fictitious trading company.
The use case is of an edge broker feeding FX pricing to client desktop/mobile devices so that they can be eyeballed. \
There are different categories of users (categories 1-4) differentiated by the refresh rates of the data.
Below is a high level architecture diagram of the distributed landscape :

![Solace AWS Architecture](/images/design/Aws-Solace.png)
The workshop will utilize the existing infrastructure, including the fully developed "Corporate data center" and "Region London (eu-west-2)". 
During the workshop, participants will construct and integrate the comprehensive "Region APAC (ap-northeast-1)" along with its various applications into the existing landscape.

By the end of this workshop, you will be able to: 

- Sign up for a Solace Cloud account
- Create a developer grade broker deployed in an AWS region
- Create an event mesh with a bidirectional link between the newly created broker and an existing broker
- Create an AWS EC2 instance and set up the required software (Java, Maven, Git, Nodejs)
- Checkout a client and admin application and set up a consumer application
- Create an AWS Lambda service which will be invoked by an EventBridge Scheduler
- Setup an AWS S3 bucket
- Use the Solace native AWS S3 connector to feed incoming events to the newly created S3 bucket
- Visualize the S3 bucket data using Amazon QuickSight


## Workshop Structure 
This workshop is divided into the sections listed below. Plan on 3-4 hours to complete the full workshop.

[x] Prerequisites : Setting up accounts for the solution *(20 minutes)* \
[x] Module 1 : Setting up a Solace broker service and event mesh integration *(20 minutes)* \
[x] Module 2 : Setting up an AWS EC2 instance, admin and client application setup *(40 minutes)* \
[x] Module 3 : Setting up AWS Lambda service and EvenBridge scheduler *(40 minutes)* \
[x] Module 4 : Setting up an AWS S3 bucket and integrate with the Solace native connector *(40 minutes)* \
[x] Module 5 : Visualize S3 data using Amazon Quicksight *(30 minutes)*

{{% notice warning %}}
The examples and sample code provided in this workshop are intended to be consumed as instructional content. These will help you understand how various AWS services can be architected to build a solution while demonstrating best practices along the way. These examples are not intended for use in production environments.
{{% /notice %}}
