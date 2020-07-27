# 1st-project
## Automated ELK Stack Deployment

The files in this repository were used to configure the network depicted below.

[C:\Users\mbhur\OneDrive\Documents\Cybersecurity-Bootcamp\1st-project\Diagrams\ElkDiagram.png
](Diagrams/ElkDiagram.png)

These files have been tested and used to generate a live ELK deployment on Azure. They can be used to either recreate the entire deployment pictured above. Alternatively, select portions of the __playbook___ file may be used to install only certain pieces of it, such as Filebeat.

  -[C:\Users\mbhur\OneDrive\Documents\Cybersecurity-Bootcamp\1st-project\Ansible\ansible_activity_playbook.txt](Ansible/ansible_activity_playbook.txt) 

This document contains the following details:
- Description of the Topologu
- Access Policies
- ELK Configuration
  - Beats in Use
  - Machines Being Monitored
- How to Use the Ansible Build


### Description of the Topology

The main purpose of this network is to expose a load-balanced and monitored instance of DVWA, the D*mn Vulnerable Web Application.

Load balancing ensures that the application will be highly _Available____, in addition to restricting __access___ to the network.
- _TODO: What aspect of security do load balancers protect?
            Load Balancers allow for the offload of request they can help protect against a DDOS attack. they also help in providing high availablility by re-routing request available servers. What is the advantage of a jump box? A jump box is a hardend asset that has security controls in place for aduiting and monitoring to track the users that entering the system. _

Integrating an ELK server allows users to easily monitor the vulnerable VMs for changes to the __Logfiles___ and system _Metrics____.
- _TODO: What does Filebeat watch for?_ Logfiles
- _TODO: What does Metricbeat record?_system metrics

The configuration details of each machine may be found below.
_Note: Use the [Markdown Table Generator](http://www.tablesgenerator.com/markdown_tables) to add/remove values from the table_.

| Name     | Function | IP Address | Operating System |
|----------|----------|------------|------------------|
| Jump Box | Gateway  | 10.0.0.4   | Linux            |
| Web 1    | WebServer| 10.0.0.7   | Linux            |
| Web 2    | WebServer| 10.0.0.6   | Linux            |
| Elk      | ElkServer| 10.1.0.4   | Linux            |

### Access Policies

The machines on the internal network are not exposed to the public Internet. 

Only the _Jump Box and Load balancer____ machine can accept connections from the Internet. Access to this machine is only allowed from the following IP addresses:
- 173.79.148.90 and 47.133.196.51_

Machines within the network can only be accessed by Jump Box_____.
- _TODO: Which machine did you allow to access your ELK VM? Jump Box 
     What was its IP address? 52.249.198.163 _

A summary of the access policies in place can be found in the table below.

| Name     | Publicly Accessible | Allowed IP Addresses |
|----------|---------------------|----------------------|
| Jump Box | Yes                 |   173.79.148.90      |
|          |                     |                      |
|          |                     |                      |

### Elk Configuration

Ansible was used to automate configuration of the ELK machine. No configuration was performed manually, which is advantageous because...
- _TODO: What is the main advantage of automating configuration with Ansible?_ 
         Automating the config file allows you to run the confiq quickley and as often as needed 

The playbook implements the following tasks:
- _TODO: In 3-5 bullets, explain the steps of the ELK installation play. E.g., install Docker; download image; etc._
- ... Add VM to the Ansible hosts file
      Create new Ansibel playbook for new Elk VM
      INcrease the virtual memory
      Install docker.io
      Install python3-pip
      Install docker
      Download and run container sebp/elk:761

- ...

The following screenshot displays the result of running `docker ps` after successfully configuring the ELK instance.

![TODO: Update the path with the name of your screenshot of docker ps output](Images/docker_ps_output.png)

### Target Machines & Beats
This ELK server is configured to monitor the following machines:
- _TODO: List the IP addresses of the machines you are monitoring
    Web1 _10.0.0.7 and web2 10.0.0.6

We have installed the following Beats on these machines:
- _TODO: Specify which Beats you successfully installed_
    installed filebeats and metricbeats 

These Beats allow us to collect the following information from each machine:
- Filebeats amd metricbeats allow you to collect system logfiles and system metrics. File beats would collect login data and we would be able to see and track successful and unsuccessful login attempts_

### Using the Playbook
In order to use the playbook, you will need to have an Ansible control node already configured. Assuming you have such a control node provisioned: 

SSH into the control node and follow the steps below:
- Copy the filebeat-config.yml_____ file to _filebeat.yml____.
- Update the _hosts____ file to include ports 5601, 9200 and 5044 
- Run the playbook, and navigate to _5601___ to check that the installation worked as expected., 

_TODO: Answer the following questions to fill in the blanks:_
- _Which file is the playbook? Where do you copy it?_
- _Which file do you update to make Ansible run the playbook on a specific machine? How do I specify which machine to install the ELK server on versus which to install Filebeat on?_
- _Which URL do you navigate to in order to check that the ELK server is running?

_As a **Bonus**, provide the specific commands the user will need to run to download the playbook, update the files, etc._