## Automated ELK Stack Deployment

The files in this repository were used to configure the network depicted below.

(Diagrams/Cloud Security Diagram.png)

These files have been tested and used to generate a live ELK deployment on Azure. They can be used to either recreate the entire deployment pictured above. Alternatively, select portions of the .yml file may be used to install only certain pieces of it, such as Filebeat.

  - my-playbook.yml

This document contains the following details:
- Description of the Topologu
- Access Policies
- ELK Configuration
  - Beats in Use
  - Machines Being Monitored
- How to Use the Ansible Build


### Description of the Topology

The main purpose of this network is to expose a load-balanced and monitored instance of DVWA, the D*mn Vulnerable Web Application.

Load balancing ensures that the application will be highly available, in addition to restricting unwanted traffic to the network.
- Load balancers protect the availbilty access of security, by protecting from DDoS attacks
- Having a jumpbox allows you to safely navigate a network

Integrating an ELK server allows users to easily monitor the vulnerable VMs for changes to the data and system logs.
-  Filebeat looks for changes in log files and log events
-  Metricbeat records metrics from the operating system and from services running on the server

The configuration details of each machine may be found below.
_Note: Use the [Markdown Table Generator](http://www.tablesgenerator.com/markdown_tables) to add/remove values from the table_.

| Name     | Function | IP Address | Operating System |
|----------|----------|------------|------------------|
| Jump Box | Gateway  | 10.0.0.4   | Linux            |
| Web-1    |Web Server| 10.0.0.5   | Linux            |
| Web-2    |Web Server| 10.0.0.6   | Linux            |
|Elk       |Elk Server| 10.1.0.4   | Linux            |
|Load Balancer| LB    | 40.117.150.142| Linux         |

### Access Policies

The machines on the internal network are not exposed to the public Internet. 

Only the Elk server machine can accept connections from the Internet. Access to this machine is only allowed from the following IP addresses:
-71.135.92.64

Machines within the network can only be accessed by the Workstation and JUmp-Box.
- Only the Jump-Box has access to the Elk server via SSH on port 22 from IP: 10.0.0.1
-My private workstation also has access via TCP on port 5601

A summary of the access policies in place can be found in the table below.

| Name     | Publicly Accessible | Allowed IP Addresses |
|----------|---------------------|----------------------|
| Jump Box | No                  | 71.135.92.64 via SSH |
| Web-1    | No                  | 10.0.0.5 via SSH     |
| Web-2    | No                  | 10.0.0.6 via SSH     |
| Elk      | No                  | 71.135.92.64 TCP 5601|
| LB       | No                  | 71.135.92.64 HTTP  80|

### Elk Configuration

Ansible was used to automate configuration of the ELK machine. No configuration was performed manually, which is advantageous because...
- The main advantage of automating configuration with Ansible is that you dont need to write custom code ot automate systems.

The playbook implements the following tasks:
- _TODO: In 3-5 bullets, explain the steps of the ELK installation play. E.g., install Docker; download image; etc._

- Increase system memory 
- Launching containers on published ports
- Install docker.io and python3-pip

The following screenshot displays the result of running `docker ps` after successfully configuring the ELK instance.

Images/docker_ps_output.png

### Target Machines & Beats
This ELK server is configured to monitor the following machines:
- 10.0.0.5: Web-1 
- 10.0.0.6: Web-2

We have installed the following Beats on these machines:
- Elk Server, Web-1 and Web-2
	-Elk Stack: Filebeat and Metricbeat

These Beats allow us to collect the following information from each machine:
- _TODO: In 1-2 sentences, explain what kind of data each beat collects, and provide 1 example of what you expect to see. E.g., `Winlogbeat` collects Windows logs, which we use to track user logon events, etc._

### Using the Playbook
In order to use the playbook, you will need to have an Ansible control node already configured. Assuming you have such a control node provisioned: 

SSH into the control node and follow the steps below:
- Copy the Ansible ELK Installation file.
- Update the _____ file to include...
- Run the playbook, and navigate to ____ to check that the installation worked as expected.

_TODO: Answer the following questions to fill in the blanks:_
- _Which file is the playbook? Where do you copy it?_
- _Which file do you update to make Ansible run the playbook on a specific machine? How do I specify which machine to install the ELK server on versus which to install Filebeat on?_
- _Which URL do you navigate to in order to check that the ELK server is running?

