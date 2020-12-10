# Unit-12-Homework
Azure Network Diagram

Description of Microsoft Azure deployment

Created Resource Group in Azure portal to create a resource group that will contain everything the Red Team needs in the cloud.

Setup Virtual Network before deploying servers and services, there must be a network where these items can be accessed.

Setup inbound security rules to block any and all traffic associated with network security groups.

Created VM 1 Jump Box with authentication type: SSH public key generated using ssh-keygen command from home PC on Git Bash.

Created VM's 2 and 3 - Web VM's running Ubuntu Server 18.04

Setup security group rule to allow SSH port 22 connections only from my current home IP address and connect to the virtual machines for management.

Configured jump box to run Docker containers and to install a container.

Created a new security group rule to allow jump box VM full access to virtual network RedTeamNet West.

Configured provisioners in jump box accessed using a new SSH key from the container running inside the jump box.
Modified the Ansible config file and hosts file
Added the python line: ansible_python_interpreter=/usr/bin/python3 besides each Web IP.

Created Ansible playbook that installed Docker and configured Web server VM's with DVWA web app.

Installed a load balancer in front of the VM to distribute the traffice among more than one VM.

configured the load balancer and security group to work together to expose port 80 of the VM to the internet.

Reach the DVWA app from browser over the internet.  http://40.78.30.232/setup.php

create a copy of VM using Ansible playbook for the configuration, and then place the VM in the backend pool for the load balancer.

Added latest Web-3 VM to the backend pool on load balancer and testing whether the website continues working if one of VM's has a problem.

Create ELK-NET virtual network located in the East region and not the same region as the other VM's.

Created VM ELK-SERVER and installed services: docker.io, python3-pip and docker.  After Docker is installed, downloaded and ran the sebp/elk:761 container.

ELK web server runs on port 5601. Created an incoming rule for ELK Server security group that allows TCP traffic over port 5601 from my home IP address.

Installed the Filebeat service on ELK server 
