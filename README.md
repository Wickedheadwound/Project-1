## Automated ELK Stack Deployment

The files in this repository were used to configure the network depicted below.

![github-small](https://github.com/Wickedheadwound/Project-1/blob/main/Diagram/Project-1.png)
These files have been tested and used to generate a live ELK deployment on Azure. They can be used to either recreate the entire deployment pictured above. Alternatively, select portions of the ELK file may be used to install only certain pieces of it, such as Filebeat.

[ELK Install yml](https://github.com/Wickedheadwound/Project-1/tree/main/Ansible)

This document contains the following details:
- Description of the Topologu
- Access Policies
- ELK Configuration
  - Beats in Use
  - Machines Being Monitored
- How to Use the Ansible Build


### Description of the Topology

The main purpose of this network is to expose a load-balanced and monitored instance of DVWA, the D*mn Vulnerable Web Application.

Load balancing ensures that the application will be highly Reliable, in addition to restricting Access to the network.
- Makes sre that the application isn't overloaded with data and restricts access to the network
- Protects webservers access to the network
- Advantage of a jupbox is that it only allows one machine/IP address to access the webservers to make any changes.

Integrating an ELK server allows users to easily monitor the vulnerable VMs for changes to the fies and system metrics.
- File beat watches for changes in the system to files
- Metric beat watches the server for activity of uptim and down time and usage.

The configuration details of each machine may be found below.
_Note: Use the [Markdown Table Generator](http://www.tablesgenerator.com/markdown_tables) to add/remove values from the table_.

| Name     | Function | IP Address | Operating System |
|----------|----------|------------|------------------|
| Jump Box | Gateway  | 10.0.0.7   | Linux            |
| web-1    |Web Server| 10.0.0.8   | Linux            |
| Web-2    |Web Server| 10.0.0.9   | Linux            |
| Web-3    |Web Server| 10.0.0.10  | Linux            |
| ELK-1    |Elk Server| 10.1.0.4   | Linux            |

### Access Policies

The machines on the internal network are not exposed to the public Internet. 

Only the Jumpbox machine can accept connections from the Internet. Access to this machine is only allowed from the following IP addresses:
The admin Public IP address

Machines within the network can only be accessed by Jumpbox.


A summary of the access policies in place can be found in the table below.

| Name     | Publicly Accessible | Allowed IP Addresses |
|----------|---------------------|----------------------|
| Jump Box  | Yes/No             | 10.0.0.7             |
| Web Server| No                 | 10.0.0.1             |
| ELK Server| No                 | 10.0.0.1             |
| Kibana    | Yes                | Public IP            |
| DVWA      | Yes                | Public IP            |

### Elk Configuration

Ansible was used to automate configuration of the ELK machine. No configuration was performed manually, which is advantageous because...
- Way faster than doing it manually.
- Updates with playbooks.

The playbook implements the following tasks:
- Installs Docker
- Enables Docker on the server
- Installs ELK data container
- Installs Python
- Installs Metricbeat
- Increases Virtual Memory

The following screenshot displays the result of running `docker ps` after successfully configuring the ELK instance.

![github-small](https://github.com/Wickedheadwound/Project-1/blob/main/Diagram/sudo%20docker%20ps.png)

### Target Machines & Beats
This ELK server is configured to monitor the following machines:
- Web-1 = IP:10.0.0.8
- Web-2 = IP:10.0.0.9
- Web-3 = IP:10.0.0.10

We have installed the following Beats on these machines:

-Filebeat
-Metricbeat

These Beats allow us to collect the following information from each machine:

- FileBeat collects the data if a file is changed, EX. When it is changed and what was changed on it by whom it was changed by
- MetricBeat collects the data of the server up time, data usage and system logins.

### Using the Playbook
In order to use the playbook, you will need to have an Ansible control node already configured. Assuming you have such a control node provisioned: 

SSH into the control node and follow the steps below:
- Copy the Instal-Elk.yml file to /etc/ansible.
- Update the host file to include...
- Run the playbook, and navigate to ____ to check that the installation worked as expected.

_TODO: Answer the following questions to fill in the blanks:_
- _Which file is the playbook? Where do you copy it?_
- _Which file do you update to make Ansible run the playbook on a specific machine? How do I specify which machine to install the ELK server on versus which to install Filebeat on?_
- _Which URL do you navigate to in order to check that the ELK server is running?

_As a **Bonus**, provide the specific commands the user will need to run to download the playbook, update the files, etc._
