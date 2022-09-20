---
title: "Admin Machine Setup"
chapter: true
weight: 5 
---
# Admin Machine Setup
In this section, we will cover how to provision your admin machine that we will be using to provision our EKS-A Bare Metal cluster on Equinix Metal. 

## Admin Machine Setup/Prerequisites

EKS Anywhere creates a Kubernetes cluster on premises to a chosen provider. Supported providers include Bare Metal (via Tinkerbell) and vSphere. To manage that cluster, you can run cluster create and delete commands from an Ubuntu or Mac Administrative machine.

Creating a cluster involves downloading EKS Anywhere tools to an Administrative machine, then running the eksctl anywhere create cluster command to deploy that cluster to the provider. A temporary bootstrap cluster runs on the Administrative machine to direct the target cluster creation. EKS-A uses the popular open-source project [Kind](https://kind.sigs.k8s.io/) to create the temporary bootstrap cluster on the admin machine. 

### Administrative machine prerequisites
- Docker 20.x.x
- Mac OS 10.15 / Ubuntu 20.04.2 LTS 
- 4 CPU cores
- 16GB memory
- 30GB free disk space

**Administrative machine must be on the same Layer 2 network as the cluster machines**

