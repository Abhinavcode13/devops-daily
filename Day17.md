## Sonar with Jenkins Integration
- SonarQube server
- Jenkins server
- On sonarqube server generate a 'Token'
- On Jenkins server
  1. Install apache maven
  2. Install sonar plugin
  3. Configure sonarqube credentials
  4. Install SonarScanner
  5. Run Pipeline Job
- Connect to jenkins VM using MobaXterm and start sonar server
- Access sonar server in browser & generate token
- Execute below commands in jenkins server VM
  1. $ su sudo
  2. $ cd /opt
  3. $ wget https://dlcdn.apache.org/maven/maven-3/3.9.6/binaries/apache-maven-3.9.6-bin.tar.gz
  4. $ tar -xvf apache-maven-3.6.3-bin.tar.gz
- Install sonar qube scanner plugin in the Jenkins.
