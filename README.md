## Automated ELK Stack Deployment

The files in this repository were used to configure the network depicted below.

![Network Diagram](https://github.com/myles1090/MylesReposi/blob/main/Diagrams/Untitled%20Diagram.drawio.pdf)

This document contains the following details:
- Description of the Topology
- Access Policies
- ELK Configuration
  - Beats in Use
  - Machines Being Monitored
- How to Use the Ansible Build


### Description of the Topology

The main purpose of this network is to expose a load-balanced and monitored instance of DVWA, the D*mn Vulnerable Web Application.

Load balancing ensures that the application will be highly reliable and available, in addition to restricting traffic to the network.
- Load balancers can defend an organization against denial-of-service (DDos) attacks. The advantage of having a jumpbox is being able to use a virtual machine that has hardended security and can manage other systems within your security sone or overal network.

Integrating an ELK server allows users to easily monitor the vulnerable VMs for changes to the logs and system traffic.
- Filebeat monitors the log files or locations that you specify.
- Metricbeat records the metrics and statistics from the operation system and from services running on the server.

The configuration details of each machine may be found below.


| Name     | Function | IP Address | Operating System |
|----------|----------|------------|------------------|
| Beat Box | Gateway  | 10.0.0.4   | Linux            |
| Web-1    |Webserver1| 10.0.0.5   | Linux            |
| Web-2    |Webserver2| 10.0.0.6   | Linux            |


### Access Policies

The machines on the internal network are not exposed to the public Internet. 

Only the Beat Box machine can accept connections from the Internet. Access to this machine is only allowed from the following IP addresses:
- 172.71.30.122

Machines within the network can only be accessed by the Beat Box VM.
- The Jump Box VM has access to the ELK VM. The IP address of the Jump Box VM is 10.0.0.4

A summary of the access policies in place can be found in the table below.

| Name     | Publicly Accessible | Allowed IP Addresses |
|----------|---------------------|----------------------|
| Jump Box |  No                 | 172.71.30.122        |
|  Web-1   |  No                 |  10.0.0.4            |
|  Web-2   |  No                 |  10.0.0.4            |
|   ELK    |  No                 |  10.0.0.4            |

### Elk Configuration

Ansible was used to automate configuration of the ELK machine. No configuration was performed manually, which is advantageous because...
- Ansible allows IT administrators to automate their daily tasks and save a lot of time. That frees them to focus on efforts that help deliver more value to the business by spending time on more important tasks.

The playbook implements the following tasks:
- Install docker
- Install python3-pip
- Install Docker python module
- Set the vm.max_map_count to 262144
- Download and launch a docker elk container



### Target Machines & Beats
This ELK server is configured to monitor the following machines:
- Web-1, 10.0.0.5
- Web-2, 10.0.0.6

We have installed the following Beats on these machines:
- Filebeat
- Metricbeat

These Beats allow us to collect the following information from each machine:

- Filebeat monitors the log files or locations that you specify, which we use to see what changes or messages the log files have received such as kill commands. Metricbeat records the metrics and statistics from the operation system and from services running on the server, which we could use to look at how much RAM or CPU usage was being used on the webservers at certain time.


### Using the Playbook
In order to use the playbook, you will need to have an Ansible control node already configured. Assuming you have such a control node provisioned: 

SSH into the control node and follow the steps below:
- Copy the ansible.cfg file to /etc/ansible
- Update the _____ file to include...
- Run the playbook, and navigate to ____ to check that the installation worked as expected.

_TODO: Answer the following questions to fill in the blanks:_
- _Which file is the playbook? Where do you copy it?_
- _Which file do you update to make Ansible run the playbook on a specific machine? How do I specify which machine to install the ELK server on versus which to install Filebeat on?_
- _Which URL do you navigate to in order to check that the ELK server is running?

_As a **Bonus**, provide the specific commands the user will need to run to download the playbook, update the files, etc._
