---
title: "Working with Cloud9 and EC2 instances" 
chapter: true
weight: 1 
---

## Introduction
In this step we will be using Cloud9 and its EC2 instance.

### Cloud9 instance
AWS Cloud9 is a cloud-based integrated development environment (IDE) that lets you write, run, and debug your code with just a browser. \
We will be using a Cloud9 backed EC2 instance to deploy our applications and consume events from over the mesh. \
As a part of this workshop, you will have already got a Cloud9 subscription setup. You can find this in your Cloud9 environments screen. 



In this step we will be learning how to :
- Create Key pairs
- Create a CloudFormation stack using an existing template file and run it
- Verify the EC2 instance created using CloudFormation stack
- Connect to the newly created EC2 instance using an SSH terminal

### Key Pairs setup
- Once you have registered for your AWS account, start off with creating SSH keypairs which will be required for this demo. \
The link over here contains detailed instructions on how to achieve this : [Create Key Pairs](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/create-key-pairs.html) \
Make sure to select the proper region : Tokyo (ap-northeast-1) for the rest of this workshop.

### EC2 instance setup using Cloudformation templates
- Within the Github repository [Solace-AWS-Integration](https://github.com/SolaceLabs/solace-aws-integration), there are Cloudformation templates available which will setup an AWS EC2 instance for this excercise.
- The link : [Run Cloudformation templates](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/resource-import-new-stack.html) defines how to setup a cloudformation stack and run from an existing template file. 
- Upload the CloudFormation template that is available from the Github repository and setup the EC2 instances for this module. 

### Verifying the EC2 instance
You should be able to see them in the EC2 instances screen as below :
![EC2 Instances](/images/moduleTwo/ec2_instances_list.png)
As you closely observe the screen you will notice: 
- The region where you are going to be working is Tokyo (ap-northeast-1)
- The instance with its id, state type and other details. 

### Connecting to the EC2 instance
- The link [Connect to EC2 instance via SSH](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/AccessingInstancesLinux.html#AccessingInstancesLinuxSSHClient) describes 
    how to connect to an EC2 instance using an SSH terminal and the keypair that you created earlier.
- Follow this step and connect to your newly created EC2 instance and login to your linux instance.
