## Apache Tomcat Server

![Tomact](https://github.com/Abhinavcode13/DevOpsDrift-Daily/assets/126642111/60449771-86de-4063-a5b5-667553267328)


- Apache tomcat is a web server
- Apache tomcat is used to run Java web applications
- Apache tomcat is free and open-source
- Apache tomcat runs on 8080 port by default

### Working with Apache Tomcat Server
- Folder structure of Tomcat
1. Bin: It containes files to start and stop the server
   1. Windows: startup.bat & shutdown.bat
   2. Linux: startup.sh & shutdown.sh
2. Conf: It containes configuration files
   1. server.xml
   2. tomcat-users.xml
3. Lib: It contains libraries (jars)
4. Logs: It contains server logs
5. Temp: It contains temporary data
6. Webapps: We will keep application war file in this folder

### Working with Apache Tomcat in Linux

![image](https://github.com/Abhinavcode13/DevOpsDrift-Daily/assets/126642111/1be8e724-ac84-479a-9aab-b801e1a9ce63)

- Login into AWS Management console
- Create Ec2 instance (Amazon linux AMI)
- Connect to Ec2 instance using MobaXterm
- Install java software using below command:
  1.` $ sudo yum install java-1.80-openjdk`
- Verify the version of the java
  1. `$ java --version`
- We can download Tomcat from the official website into ec2 VM machine (https://tomcat.apache.org/download-90.cgi)
- Copy the URL of tar file and execute below command in linux machine
  1. `$ wget https://dlcdn.apache.org/tomcat/tomcat-9/v9.0.84/bin/apache-tomcat-9.0.84.tar.gz`
  2. `$ tar -xvf apache-tomcat-9.0.84.tar.gz` (for extraction of tar file)
- Go inside the tomcat folder and see folder structure
  1. `$ cd tomcat-server`
  2. `$ ls -ltr`
- Go to tomcat bin directory and run tomcat server
  1. `$ cd bin`
  2. `$ ./startup.sh`
- Note: Tomcat server runs on 8080 port by default. Enable this port in security group as custom TCP.
  1. Type: `Custom TCP`
  2. Protocol: `TCP`
  3. Port Range: `8080`
  4. Source: `Custom(0.0.0.0/0)`
- Access the tomcat server from your browser
  1. URL: `https://Ec2-vm-public-ip:8080/`
  2. Note: It should open tomcat server open page
- By default the host manager is only accessible from a browser running on the same machine as Tomcat. If you wish to modify this restriction, you'll need to edit the Host manger context.xml file.
- File location: `<tomcat>/webapps/manager/META-INF/context.xml` , then do vi context.xml
- In Manager context.xml file, change <Value> section like below (allow sttribute value changed)
- In allow set it as ".*" then save it.
- Add tomcat users in `tomcat/conf/tomact-useers.xml` file like shown below:
  1. < role rolename= "manager-gui" />
  2. < user username= "tomcat" password="tomcat" roles="manager-gui" />
  3. < role rolename= "admin-gui" />
  4. < user username= "admin" password="admin" roles="manager-gui",admin-gui" />
- After doing the mentioned changes stop tomcat server
  1. $ cd bin
  2. $ ./shutdown.sh
- Create a maven application
- Edit index.jsp file like below (file location: project-folder\src\main\webapp)
```
<html>
<body>
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Bold and Red Text</title>
</head>
<body>
    <p><strong style="color: red;">This text is bold and red.</strong></p>
</body>
</html>
```
- Package maven web application as war file using maven goals.
  1. mvn clean package
- Go to tomcat Server Admin Dashboard and click on "Manager App"
- Select War file to upload and click on 'deploy' button
- Click on Application path
- Stop Tomcat server
- Stop Ec2 instance in AWS
