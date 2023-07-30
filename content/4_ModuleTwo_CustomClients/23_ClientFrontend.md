---
title: "Setup and run the client frontend"
chapter: true
weight: 3
---

## Introduction
In this step we will be learning how to :
- Understanding the functionalities of the FX price client application
- Install the following on an EC2 instance:
    - Docker
    - Docker compose
- Modify the configuration properties as required
- Build and run the client application
- Walk through the application

### Understand the functionalities of the FX price client application
In this workshop, our primary use case involves an edge broker that provides FX pricing to client desktop and mobile devices for easy access and review.

Users are divided into different categories (categories 1-4) based on the refresh rates of the data they receive. \
This rate limiting is implemented using the concept of Direct Messaging Eliding backed by client profiles with the corresponding message delays. \
This client application is built using Angular and the Solace Nodejs API and deployed in a docker container within the EC2 instance. 

### Installing development tools
In the previous step, you had successfully connected to your EC2 instance using an SSH terminal.
To build and run the client application, you will need some development tools namely :

#### Docker
Following are the set of commands need to be executed sequentially to install Docker :

`sudo yum install docker -y`

To start the Docker service, run `sudo service docker start`.

#### Docker compose
Following are the set of commands need to be executed sequentially to install Docker compose :

`sudo curl -L https://github.com/docker/compose/releases/latest/download/docker-compose-$(uname -s)-$(uname -m) -o /usr/local/bin/docker-compose`

`sudo chmod +x /usr/local/bin/docker-compose`

To verify the installation, run `docker-compose version`.

### Codebase of the frontend application
The frontend application is already checked out and present within the repository that you cloned in the earlier step.

Navigate to the directory : `cd solace-aws-integration/solace-quoteappdemo-frontend`

### Modifying configuration properties
Similar to the Admin application, you will have to update some of the configuration properties that are required for the application to connect and start off.
Navigate to the location of the file : `cd src/environments/`

Enter the file using the command : `vi environment.ts` \
Within the file, press `i` to enter the Insert mode \
Change the following parameters with the values that you have collected earlier in Module-1 for the Angular frontend application:
- host : Public Endpoint
- vpn : Message VPN
- clientUserName : Username
- clientPassword : Password 
- uri : The public IP of the EC2 instance that you have created 

Once you have updated all the values successfully, press the **Escape(esc)** key to exit the Insert mode \
Press `:wq!` to save and exit the file.

To confirm that you have made all the changes properly, enter the file again using the command `vi environment.ts` \
Verify the changes and press `:q!` to exit the file without making any changes. 

### Build and run the Administration application
Navigate back to the root of the _solace-quoteappdemo-frontend_ application using the following command : `cd ../../` \
Build and run the application using the command  : `sudo docker-compose up --build`

Once the application shows up as started, you can hit the different urls of the client applications like below :
- Refresh rate - 1 : [http://EC2_PUBLIC_IP:7888/?elidingType=level1](http://EC2_PUBLIC_IP:7888/?elidingType=level1)
- Refresh rate - 2 : [http://EC2_PUBLIC_IP:7888/?elidingType=level2](http://EC2_PUBLIC_IP:7888/?elidingType=level2)
- Refresh rate - 3 : [http://EC2_PUBLIC_IP:7888/?elidingType=level3](http://EC2_PUBLIC_IP:7888/?elidingType=level3)
- Refresh rate - 4 : [http://EC2_PUBLIC_IP:7888/?elidingType=level4](http://EC2_PUBLIC_IP:7888/?elidingType=level4)


