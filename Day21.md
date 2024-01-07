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
