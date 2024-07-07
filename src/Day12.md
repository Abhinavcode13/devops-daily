## Jenkins
- Jenkins is an open source automation tool for CI/CD.
- Jenkins is developed by Java.
### Continuos integration / Continuos deployment
- CI and CD are two most frequently used terms in mordern development practices and Devops practices.
- CI stands for continuos integration. It is fundamental concept of DevOps where developers frequently merge code changes to central repository where automated builds and test run.
- CD means continuos delivery or continuos deployment.
- Jenkins is a self-contained, open-source automation server which can be used to automate all sorts of tasks related to building, testing and delivering or deploying software.

### Build & Deployment Process
1. Take latest source code from repository.
2. Compile source code
3. Execute unit test
4. Perform code review
5. Package code as war file
6. Deploy the war file into the server
Note: All the above Build & Deployment Process can be done automatically using jenkins tool.

### Jenkins Installation on AWS ec2 
- Add jenkins repo to your yum repository
  1. $ sudo wget -O /etc/yum.repos.d/jenkins.repo https://pkg.jenkins.io/jenkins.repo
- Import a key file from Jenkins-CLI to enable installation from the package
  1. $ sudo rpm --import https://pkg.jenkins.io/redhat-stable/jenkins.io-2023.key
- For amazon linux
  1. sudo amazon-linux-extras install epel
- Install jenkins
  1. $ sudo yum install jenkins -y
- Start and enable jenkins services
  1. $ sudo systemctl start jenkins
  2. $ sudo systemctl enable jenkins
  3. $ sudo systemctl status jenkins
  4. $ sudo cat /var/lib/jenkins/secrets/initialAdminPassword
- Note: Make sure that you have configured 8080 port in Security group inbound rules which is attached to ec2 instance.
- Access jenkins using the URL: http://public-ip:8080/




