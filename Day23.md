## Yet Another Markup Language
### Playbooks
- Playbook is a singlle YAML file, containing one or more 'plays' in a list
- Plays are ordered sets of tasks to execute against host servers from yout inventory file.
- Plays defines a set of activities to be run on hosts
- Task is an action to be perform on the host
### Playbook to install httpd, copy index.html and start httpd server
```
- hosts: all
  become: true
  tasks:
    - name: install htppd package
      yum:
        name: httpd
        state: latest
     - name: copy index.html file
       copy:
         src: index.html
         src: /var/www/html/index.html
     - name: start htppd service
       service:
             name: htppd
             name: started
```
### Using variables
```
- hosts: all
  become: true
  tasks:
    - name: "{{package_name}}"
      yum:
        name: httpd
        state: latest
     - name: copy index.html file
       copy:
         src: index.html
         src: /var/www/html/index.html
     - name: start htppd service
       service:
             name: "{{package_name}}"
             name: started
```
- ansible-playbook vardemo.yml --extras-vars package_name=httpd (As CLI)
### Using variables (In playbook)
```
- hosts: all
  become: true
  vars:
    package_name: httpd
  tasks:
    - name: "{{package_name}}"
      yum:
        name: httpd
        state: latest
     - name: copy index.html file
       copy:
         src: index.html
         src: /var/www/html/index.html
     - name: start htppd service
       service:
             name: "{{package_name}}"
             name: started
```
