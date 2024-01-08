## Ansible AD-Hoc commands
- Syntax : `$ ansible [all/groupname/hostname/ip] -m module-name -a arguements`
- Ping all host servers : `$ ansible all -m ping`
- Ping all web servers host nodes : `$ ansible webservers -m ping`
- Ping particular ip : `$ ansible 172.132.1.8 -m ping`
- Print date from webservers group : `$ ansible webservers -m shell -a 'date'`
- Print disk space of all host nodes : `$ ansible all -m shell -a 'du -h'`
- Check git version in all host nodes : `$ ansible all -m shell -a 'git --version'`
