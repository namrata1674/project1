# project1Project 1 Elk Stack Deployment
This repository is a description and layout guide for a Live ELK (Elasticsearch, Logstash, and Kibana.) Deployment created during the University of Utah Cyber Security Bootcamp.
This Diagram Shows the Layout of the Network: 
These Ansible Playbook files are tested and can be used to setup a live ELK deployment on Azure. There are separate playbooks for each part of the ELK deployment, so using only certain parts such as just filebeat is also an option.

This Document Contains:
Topology Description
Access Polices
Elk Configuration
Elk Target Machines
Ansible setup
Topology:
The use of this network is to show a load-balanced and monitored version of the DVWA, D*amn Vulnerable Web Application.
The Load Balancing makes the app stable and restricts accesss to unauthorized users.
Adding ELK (Elastisearch, Logstash and Kibana) allows easy monitoring of the vulnerable VM's for changes in the Logs and system.
This Table shows the configuration of VMs on the Network.
Name
Function
IP Address
Operating System
Jump Box
Gateway
10.0.0.4
Linux
web-01
Webserver
10.0.0.5
Linux
web-02
Webserver
10.0.0.6
Linux
web-03
Webserver
10.0.0.7
Linux
Elk-Server
Webserver
10.1.0.4
Linux

Access Policies
The VMs on the internal network are not accessable from the public internet. Only the Jumpbox VM accepts connections from the internet and only from specified IPs. The Current configuration for set for the jumpbox to only accept the users home IP address. Machines in the network are accessed only through the jumpbox. 
Elk Configuration
To automate and make the setup process easier, Ansible playbooks were used for configuration. This makes scaling the webservers and redploying simple and fast, as no manual configuration needs to be done.
The Ansible Playbooks do the following tasks:
Downloads Docker
Downloads Python
Downloads and installs the Docker Container
Sets up Docker to start on restart

Elk Target Machines
The Elk Server is setup to monitor the following VMs with FileBeat and MetricBeat
Name
Function
IP Address
Operating System
web-01
Webserver
10.0.0.5
Linux
web-02
Webserver
10.0.0.6
Linux
web-03
Webserver
10.0.0.7
Linux

Ansible Setup
To use the playbooks, you will need to have an Ansible Control node configured, if you have access to one.
SSH to the control node and follow these steps:
Copy the ansible playbook file to /etc/ansible
Update the hosts file to your websever IP address
Run the playbook, and check to verify install was successful.
