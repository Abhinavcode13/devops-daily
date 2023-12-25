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
- Login into AWS Management console
- Create Ec2 instance (Amazon linux AMI)
- Connect to Ec2 instance using MobaXterm
- Install java software using below command:
  1. $ sudo yum install java-1.80-openjdk
- Verify the version of the java
  1. $ java --version
- We can download Tomcat from the official website into ec2 VM machine (https://tomcat.apache.org/download-90.cgi)
- Copy the URL of tar file and execute below command in linux machine
  1. $ wget https://dlcdn.apache.org/tomcat/tomcat-9/v9.0.84/bin/apache-tomcat-9.0.84.tar.gz
  2. $ tar -xvf apache-tomcat-9.0.84.tar.gz (for extraction of tar file)
- Go inside the tomcat folder and see folder structure
  1. $ cd tomcat-server
  2. $ ls -ltr
- Go to tomcat bin directory and run tomcat server
  1. $ cd bin
  2. $ ./startup.sh
- Note: Tomcat server runs on 8080 port by default. Enable this port in security group as custom TCP.
  1. Type: Custom TCP
  2. Protocol: TCP
  3. Port Range: 8080
  4. Source: Custom(0.0.0.0/0)
- Access the tomcat server from your browser
  1. URL: https://Ec2-vm-public-ip:8080/
  2. Note: It should open tomcat server open page
