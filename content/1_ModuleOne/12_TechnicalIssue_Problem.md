---
title: "Technical Issue / Problem" # MODIFY THIS TITLE
chapter: true
weight: 2 # MODIFY THIS VALUE TO REFLECT THE ORDERING OF THE MODULES IF APPLICABLE
---

# Technical Issue / Problem <!-- MODIFY THIS HEADING TO REFLECT THE PROBLEM THE WORKSHOP IS ADDRESSING -->

## Submodule Two Heading <!-- MODIFY THIS SUBHEADING -->
This paragraph block should be an introduction to the technical issue the solution is facing. An example of this can be seen at the bottom of this page. <br>

{{% notice info %}}
<p style='text-align: left;'>
**REMOVE:** With the exception of _index.md, the module folders and filenames should be changed to better reflect their content, i.e. 1_Planning as the folder and 11_HowToBegin as the first submodule. Changing the "weight" value of the header is ultimately what reflects the order the modules are presented.
</p>
{{% /notice %}}

### Next Section Heading <!-- MODIFY THIS HEADING -->
This paragraph block can optionally be utilized to lead into the next section of the workshop.


#### Example of content guidance

# Deploy Without Worry

## Deployments with Kubernetes?

Kubernetes (k8s) is a container orchestration platform allowing organizations to scale their services and workloads quickly. If you are working with containers or microservices, k8s may be a great use case for you. Kubenetes deployments are container image deployments which target k8s-based environments.

Amazon has released a managed k8s service called Elastic Kubernetes Service (EKS). Amazon EKS helps you provide highly-available and secure clusters and automates key tasks such as patching, node provisioning, and updates. While AWS provides the platform on which to run your containerize applications deploying them in a scalable, repeatable and reliable way is where Harness comes in.


## How does Harness help with EKS deployments?

Harness has first-class support for Kubernetes Resources. Harness can create scaffolding around Kubernetes Resources removing complexities around crafting your own resource definitions that are purpose made for deployments. Harness can offer granular deployment lifecycle support around different Kubernetes Resources supporting canary and blue/green deployments inside Kubernetes.

## Why is Canary deployment tricky with EKS deployments?

Canary Deployments are a progressive delivery pattern for rolling out releases to a subset of users. Canary Deployments can be complex because of the multiple phases and the judgment call of when to promote or rollback a canary. The Harness Platform has smart verification taking away the manual toil in verification and enables seamless Canary Deployments.