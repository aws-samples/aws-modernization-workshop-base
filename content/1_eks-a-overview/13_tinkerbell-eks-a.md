---
title: "Tinkerbell in EKS Anywhere Bare Metal"
chapter: true
weight: 3 
---
# Tinkerbell in EKS Anywhere Bare Metal
## Overview of Tinkerbell in EKS Anywhere Bare Metal 
When you run the command to create an EKS Anywhere Bare Metal cluster, a set of Tinkerbell components start up on the Admin machine. One of these components runs in a container on Docker, while other components run as either controllers or services in pods on the Kubernetes kind cluster that is started up on the Admin machine. Tinkerbell components include boots, hegel, rufio, and tink. In this section, we will cover how each of these microservices operate in the context of EKS Anywhere Bare Metal. 

### Boots
The boots service runs in a single container to handle the DHCP service and Netbooting activities. In particular, boots hands out IP addresses, serves iPXE binaries via HTTP and TFTP, delivers an iPXE script to the provisioned machines, and runs a syslog server.

Boots is different from the other Tinkerbell services because the DHCP service it runs must listen directly to layer 2 traffic. (The kind cluster running on the Admin machine doesn’t have the ability to have pods listening on layer 2 networks, which is why boots is run directly on Docker instead, with host networking enabled.)

### Tinkerbell Hegel, Rufio, and Tink components
After boots comes up on Docker, a small Kubernetes kind cluster starts up on the Admin machine. Other Tinkerbell components run as pods on that kind cluster. Those components include:

- **hegel**: Manages Tinkerbell’s metadata service. The hegel service gets its metadata from the hardware specification stored in Kubernetes in the form of custom resources. The format that it serves is similar to an Ec2 metadata format.
- **rufio**: Handles talking to BMCs (which manages things like starting and stopping systems with IPMI). The rufio Kubernetes controller sets things such as power state, persistent boot order, and eventually other services (like NTP, LDAP, and TLS certificates). BMC authentication is managed with Kubernetes secrets.
- **tink**: The tink service consists of three components: tink server, tink controller, and tink worker. The tink controller manages hardware data, templates you want to execute, and the worflows that each target specific hardware you are provisioning. The tink worker is a small binary that runs inside of HookOS and talks to the tink server. The worker sends the tink server its MAC address and asks the server for workflows to run. The tink worker will then go through each action, one-by-one, and try to execute it.

## Next Section - Equinix Metal Setup
Now that we understand the various microservices that make up the Tinkerbell Infrastructure Stack and how EKS-A Bare Metal leverages Tinkerbell, we can move on to setting up our lab environment for the rest of this workshop. 