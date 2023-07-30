---
title: "S3 bucket setup"
chapter: true
weight: 1 
---

## Introduction
In this section we will be creating a S3 bucket and an access-key/access-key-secret for the next step.

### Creating a S3 bucket
- Open the [S3 page](https://s3.console.aws.amazon.com/s3/) of the console
- Click on **Create bucket** on the right side
- Create a new bucket with the name : `solace-aws-stock-bucket`
- Choose the AWS Region : **Asia Pacific (Tokyo) ap-northeast-1**
- Make sure to **Allow public access**
- Click **Create bucket**
Refer to the screenshots for reference.

![S3 - Create-bucket](/images/moduleFour/S3-create-bucket-screen-1.png)

![S3 - Create-bucket - Allow Access](/images/moduleFour/S3-create-bucket-screen-2.png)

### Creating access key/access-key-secret
To be able to persist items to the newly created bucket, we will be using the Solace-S3 native connector. \
This native connector requires an access-key and its secret which we will be setting up now.

- Open the [IAM page](https://us-east-1.console.aws.amazon.com/iamv2) of the console
- Goto the **My security credentials** using the quick links on the right
- Scroll down to the **Access keys** section and click on **Create access key**
- Create an access key pair which consists of an access key and the secret access key
- Copy the pair and store it securely for the next step

