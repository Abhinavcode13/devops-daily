## Working with variables in ansible
![image](https://github.com/Abhinavcode13/DevOpsDrift-Daily/assets/126642111/7d223e59-8d7f-41d7-ab0f-447fc97a5be1)

## Ansible Vaults
- It is is used to secure our data
- When we configure username and password in variables files everybody can see them which is not a good practise.
- When dealing with sensitive data which should secure it.
- Using ansible vault we can secure and protect the data.

### Ansible vault commands
- $ ansible-vault create test.yml - To create ansible vault
- $ ansible-vault encrypt foo.yml - To Encrypting Unencrypted Files
- $ ansible-vault decrypt foo.yml - To Decrypting Encrypted Files
- $ ansible-vault edit foo.yml - To edit the file
- $ ansible-vault view foo.yml - To view the file
- $ ansible-vault rekey foo.yml - To rekey/change the file

### Tags and handlers
Ansible tags are another useful feature that can assist you in carrying out specific tasks from the playbook. By default, all tasks in the playbook are executed, but we can control this behaviour with tags and execute only the tasks with the matching tags.

```
--- 
- name: Usage of tags
  hosts: all
  tasks:
   - name: httpd install
     yum: 
      name: httpd
      state: latest
     tags:
      - httpd
   - name: download the httpd.conf
     get_url:
      url: https://www.haio.ir/app/uploads/2021/12/Ansible-for-DevOps-by-Jeff-Geerling-z-lib.org_.pdf
      dest: /var/www/html/ansible.pdf
      mode: 0644
     notify:
      - restart httpd
     tags:
      - httpd
   - name: install vsftpd
     yum:
      name: vsftpd
      state: latest
     tags:
      - vsftpd
   - name: start the service
     service:
      name: vsftpd
      state: restarted 
     tags:
      - vsftpd  
  handlers:
   - name: restart httpd
     service:
      name: httpd
      state: restarted
      enabled: yes
```     
- Let us now execute the following commands to better understand tags after we have tagged the modules into groups.
```
ansible-playbook <playbook name> --list-tags (To list all the tags)

ansible-playbook <playbook name> --tags (To execute the paticular tag or tags)

ansible-playbook <playbook name> --list-tasks (To list the tasks)

ansible-playbook <playbook name> --skip-tags (To skip the tag or tags)

ansible-playbook <playbook name> --step (It will ask whether to continue the tag)
```

![image](https://github.com/Abhinavcode13/DevOpsDrift-Daily/assets/126642111/fab07397-8915-46e6-a537-8b8202a21e42)
