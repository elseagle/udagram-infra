
# Udagram

## About
This project has the deployment infrastructure for Udagram app

## Server specs

- Launch Configuration was created for the application servers in order to deploy four servers
- Two located in each of your private subnets. 
- The launch configuration is used by an auto-scaling group.
- Two vCPUs and at least 4GB of RAM. 
- The Operating System used is Ubuntu 18.
- 10GB of disk space.

## Security Groups and Roles


- IaM role is created for s3 bucket listing
- Udagram communicates on the default HTTP Port: 80, so your servers will need this inbound port open since you will use it with the Load Balancer and the Load Balancer Health Check. As for outbound, the servers will need unrestricted internet access to be able to download and update their software.
- The load balancer should allow all public traffic (0.0.0.0/0) on port 80 inbound, which is the default HTTP port. Outbound, it will only be using port 80 to reach the internal servers.
- The application needs to be deployed into private subnets with a Load Balancer located in a public subnet.
- One of the output exports of the CloudFormation script should be the public URL of the LoadBalancer.
-  http:// added in front of the load balancer DNS Name in the output, for convenience.

## Folders
- `model`: the architecture diagram is here
- `utils`: bash scripts for creating, updating and deleting stack


## Core Files
- `param-network.json`: parameters for network
- `param-server.json`: parameters for server
- `config-network.yml`: configurations for network
- `config-server.yml`: configurations for server



