## Steps to create jenkins with git repo + Maven + Tomcat server

- Go to tomcat server folder and configure below users intomcat-users.xml file (In conf folder)

![image](https://github.com/Abhinavcode13/DevOpsDrift-Daily/assets/126642111/84c12e92-0a4f-410b-b6d2-1bdb31e92203)

```
1. <role rolename= "manager-gui" />
2. <user username= "tomcat" password="tomcat" roles="manager-gui" />
3. <role rolename= "admin-gui" />
4. <role rolename= "manager-script" /> (New role)
5. <user username= "admin" password="admin" roles="manager-gui,admin-gui,manager-script" />
```
- Check status of jenkins : $ sudo systemctl jenkins status
- Go to jenkins dashboard -> Manage jenkins -> Manage plugins -> Available -> search for "Deploy Conatiner" Plugin -> Install it
- Create Jenkins job
  - New Item
  - Enter Item name
  - Enter some description
  - Don't give anything in 'General' section
  - Go to "Source code management" Tab and " Select "Git"
  - Don't give anything for Build triggers section. (If given Poll SCM and in schedule as ***** it will build whenever the code is changed.)
  - Enter Project "Git repo url"
  - Add your Github account credentials
  - In build environment select 'Delete workspace before build starts'
  - Go to "Build tools"
  - Click on add build step and select 'Invoke Top level Maven Targets'
  - Select Maven and enter goals 'clean package'
  - Click on 'Post Build Action' and Select 'Deploy war/ear to container' option
  - Give path of war file (It can be given like this also **/*.war)
  - Enter context path (Give project name)
  - Click on'Add Container' and select Tomcat version 9.x remote
  - Add tomcat server credentials (give the username & pwd which is having manager-script role)
  - Enter tomcat server URL (https://ec2-public-ip:serverport)
  - Click on Apply and Save
- Click on build now it will execute the pipeline.
- It will show 'Build Success' if everything is fine.
