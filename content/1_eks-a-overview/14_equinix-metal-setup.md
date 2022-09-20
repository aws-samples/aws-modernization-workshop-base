---
title: "Equinix Metal Setup" 
chapter: true
weight: 4 
---

# Equinix Metal Account Setup
We will be leveraging Equinix Metal as our lab environment to go through the rest of this workshop. Equinix Metal is a bare metal as-a-service (BMaaS) offering which allows customers to rapidly and virtually provision physical servers at Equinix's data centers around the globe. In this section we will go over how to set up an Equinix Metal account. To learn more about Equinix Metal, visit [link](https://metal.equinix.com/).

### Account Setup
Visit this [link](https://metal.equinix.com/start/) to sign up for an Equinix Metal account. Follow the directions and enter the promo code **LETSGOSURFING** to add credits into your account. 

{{% notice warning %}}
Please note that the promo code above provides a limited amount of credits and that after those credits run out, you will be charged for usage. We recommend that you closely monitor the instances that are spun up as part of this workshop and to deprovision all resources once you have completed this workshop. AWS is not financially responsible for any cost incurred throughout this workshop or for any resources provisioned on Equinix Metal. 
{{% /notice %}}

### Add SSH Keys to Account
The next step we need to complete is generating SSH keys to add to our account. We will need these SSH keys so that we can SSH into our admin machine that we will be using to provision our EKS-A cluster. Follow the steps outlined in this [link](https://metal.equinix.com/developers/docs/accounts/ssh-keys/) to create and add new SSH keys to your Equinix Metal account.

{{% notice warning %}}
Do not share the SSH keys that are created as part of this workshop. 
{{% /notice %}}

### Next Section - Setup Admin Machine
Now that we have our Equinix Metal account ready for use, the next step will cover how to set up our admin machine and the various tools/utilities we will need to set up our first EKS-A cluster. 
