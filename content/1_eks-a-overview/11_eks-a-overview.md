---
title: "Introduction to EKS Anywhere (EKS-A)"
chapter: true
weight: 1 
---
# Introduction to EKS Anywhere (EKS-A)
## EKS Anywhere (EKS-A) Overview 

Amazon EKS Anywhere is a new deployment option for Amazon EKS that allows customers to create and operate Kubernetes clusters on customer-managed infrastructure, supported by AWS. Customers can now run Amazon EKS Anywhere on their own on-premises infrastructure using Bare Metal or VMware vSphere. **Note that this workshop will be focused EKS-A Bare Metal**

Amazon EKS Anywhere helps simplify the creation and operation of on-premises Kubernetes clusters with default component configurations while providing tools for automating cluster management. It builds on the strengths of Amazon EKS Distro: the same Kubernetes distribution that powers Amazon EKS on AWS. AWS supports all Amazon EKS Anywhere components including the integrated 3rd-party software, so that customers can reduce their support costs and avoid maintenance of redundant open-source and third-party tools. In addition, Amazon EKS Anywhere gives customers on-premises Kubernetes operational tooling that’s consistent with Amazon EKS. You can leverage the EKS console to view all of your Kubernetes clusters (including EKS Anywhere clusters) running anywhere, through the EKS Connector (public preview)

### Benefits and Use Cases

Here are some key customer benefits of using Amazon EKS Anywhere:

- **Simplify on-premises Kubernetes management** - Amazon EKS Anywhere helps simplify the creation and operation of on-premises Kubernetes clusters with default component configurations while providing tools for automating cluster management.
- **One stop support** - AWS supports all Amazon EKS Anywhere components including the integrated 3rd-party software, so that customers can reduce their support costs and avoid maintenance of redundant open-source and third-party tools.
- **Consistent and reliable** - Amazon EKS Anywhere gives you on-premises Kubernetes operational tooling that’s consistent with Amazon EKS. It builds on the strengths of Amazon EKS Distro and provides open-source software that’s up-to-date and patched, so you can have a Kubernetes environment on-premises that is more reliable than self-managed Kubernetes offerings.

### Use-Cases Support by EKS Anywhere
EKS Anywhere is suitable for the following use-cases:

* **Hybrid cloud consistency** - You may have lots of Kubernetes workloads on Amazon EKS but also need to operate Kubernetes clusters on-premises. Amazon EKS Anywhere offers strong operational consistency with Amazon EKS so you can standardize your Kubernetes operations based on a unified toolset.
- **Disconnected environment** - You may need to secure your applications in disconnected environment or run applications in areas without internet connectivity. Amazon EKS Anywhere allows you to deploy and operate highly-available clusters with the same Kubernetes distribution that powers Amazon EKS on AWS.
- **Application modernization** - Amazon EKS Anywhere empowers you to modernize your on-premises applications, removing the heavy lifting of keeping up with upstream Kubernetes and security patches, so you can focus on your core business value.
- **Data sovereignty** - You may want to keep your large data sets on-premises due to legal requirements concerning the location of the data. Amazon EKS Anywhere brings the trusted Amazon EKS Kubernetes distribution and tools to where your data needs to be.

### Next section - Tinkerbell Overview
In the next section, we will go over how EKS-A Bare Metal uses the open-source project Tinkerbell to provision Kubernetes nodes on bare metal machines. 