## Ansible

![image](https://github.com/Abhinavcode13/DevOpsDrift-Daily/assets/126642111/24b66b52-3f41-4ad9-8727-17a4ca701aca)


- Ansible is an open-source automation tool, or platform, used for IT tasks such as configuration management
- Free: Ansible is an open-source tool.
- This tool is very simple to use yet powerful enough to automate complex multi tier application environments.
- Infrastructure as code(IaC) simply means that managing the infrastructure by writing ode than using manual process.
- The best part of this is you don't need to know the commands used to accomplish a particular task
- You just need to specify that what state you want the system to be in and Ansible will take care of it.
- The main components of Ansible are playbooks, configuration management and deployment.
- Earlier we used to have systemadmin for project who was responsible to manage configurations required for machines manually.
- If we have 100s of machines then it will be very difficuilt to manage
- It uses playbooks to automate deploy, manage, build.
 
### Features
- Ansible manages machines in an agent-less manner using SHH
- Built on top of python and hence a lot of python functionlity
- YAML based playbooks
- Uses SSH for secure connections
- Follows push based architecture for sending information
### Inventory file 
- Comment begins with '#' character
- Blank lines are ignore
- Groups of hosts are delimited by '[header]' elements
- You can enter hostname oor ip addresses
- A hostname/ip can be member of multiple groups
- Ungrouped hosts are specifying before any group headers like below
- Ansible inventory hosts file is used to list the groups your servers. Its deafult location is /etc/ansible/hosts
- Note: In inventory file we can mention IP addresses or hostname also.
### Sample inventory file example
```
192.168.122.1 
192.168.122.2
192.168.122.3

[webservers]
192.168.122.1
#192.168.122.2
192.168.122.3

[dbserver]
192.168.122.1
192.168.122.2
juggler-db1.com
juggler-db2.com
```
### Different configuration management tools in Devops
- Chef and Puppet works based on `PULL` mechanism
- Ansible works based on `PUSH` mechanism
