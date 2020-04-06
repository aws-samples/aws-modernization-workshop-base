+++
title = "Cleanup"
chapter = false
weight = 10
+++

### Cleanup 
{{% notice warning %}}
In order to prevent charges to your account we recommend cleaning up the infrastructure that was created. If you plan to keep things running so you can examine the workshop a bit more please remember to do the cleanup when you are done. It is very easy to leave things running in an AWS account, forget about it, and then accrue charges.
{{% /notice %}}

In the AWS console, go to [CloudFormation](https://us-west-2.console.aws.amazon.com/cloudformation/home?region=us-west-2), click `ModernizationWorkshop` stack and then `Delete`

Verify that none of the Workshop* stacks are listed in CloudFormation and you are done.





