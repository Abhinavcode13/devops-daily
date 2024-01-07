## Ansible Setup
- Create 2 Redhat system in AWS
- Connect to all systems and create ansible user
- $ sudo useradd ansible
- $ sudo passwd ansible
- $ pwd
- $ confirm pwd
- $ sudo visudo
- ADD ansible ALL=(ALL) NOPASSWD: ALL
- $ sudo vi/etc/ssh/sshd_conifg
  1. comment the PasswordAuthentication no
  2. un-comment PasswordAuthentication yes
  3. Restart the server
### Install ansible in master node
- $ sudo su ansible
- $ sudo yum install python (install python)
- $ python3 --version
- $ sudo yum -y install python3-pip
- Install ansible using python pip
- pip3 install ansible --user
- $ ansible --version
- $ sudo mkdir etc/ansible
- create ansible.cfg file under /etc/ansible and paste complete content from below git link.
- Opne : https://raw.githubusercontent.com/ansible/ansible/devel/examples/ansible.cfg
- $ sudo vi /etc/ansible/ansible.cfg
- Add inventory file to hosts
- $ sudo vi /etc/ansible/hosts
```
Host file
ungrouped:
  hosts:
    mail.example.com:
webservers:
  hosts:
    foo.example.com:
    bar.example.com:
dbservers:
  hosts:
    one.example.com:
    two.example.com:
    three.example.com:
east:
  hosts:
    foo.example.com:
    one.example.com:
    two.example.com:
west:
  hosts:
    bar.example.com:
    three.example.com:
prod:
  hosts:
    foo.example.com:
    one.example.com:
    two.example.com:
test:
  hosts:
    bar.example.com:
    three.example.com:
```
- Ansible setup is completed

### Update host inventory in ansible server to add host server details to test connection.
- $ sudo vi /etc/ansible/hosts
- Connect using username and password
  1. $ HOST-NODE-IP ansible_user=ansible ansible_password=hello1123
  2. $ ansible all -m ping
