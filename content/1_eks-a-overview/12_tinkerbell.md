---
title: "Tinkerbell Overview"
chapter: true
weight: 2 
---

# Tinkerbell Overivew

## What is Tinkerbell?

Tinkerbell is a bare metal provisioning engine, built and maintained by the team at Tinkerbell Community (contributed to the Linux Foundation by Equinix Metal). Tinkerbell consists of five microservices: Boots, Hegel, Hook, PBnJ, and Tink.

![Partner Logo](/images/tinkerbell.jpeg)

### How does Tinkerbell work?

![Partner Logo](/images/tinkerbell2.jpeg)

Tinkerbell has four major components: a DHCP server (Boots), a metadata service (Hegel), an in-memory operating system installation environment (Hook) and a workflow engine (Tink). There is also an optional fifth component useful in VM and server setups: a Power and Boot service (PBnJ) that communicates with BMCs. The workflow engine is comprised of a server and a CLI, which communicate over gRPC. The CLI is used to create a workflow along with its building blocks, templates and targets.

The additional component that you will notice that is leveraged by EKS-A Bare Metal is a microservice known as Rufio. Rufio is a Kubernetes controller for managing baseboard management controllers in a Tinkerbell context and the goals Rufio was built to achieve is listed as follows:

- Provide baseboard management controller operations necessary for bare metal provisioning.
- Provide insight into baseboard management information that is useful in bare metal provisioning contexts.
- Integrate seamlessly with the Kubernetes capable components of Tinkerbell.

## Next section - Tinkerbell in EKS Anywhere
In the next section we will cover how EKS Anywhere Bare Metal leverages the Tinkerbell Infrastructure Stack to provsion EKS Anywhere on bare metal machines. 


