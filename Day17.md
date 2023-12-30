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
- Manage jenkins -> configure system -> Sonar qube servers -> Add sonar qube server
  - Name : Sonar-Server-7.8
  - Server URL : (sonar-server-url)
  - Add sonar server token
- Manage Jenkins -> global tools configuration -> SonarQube scanner
  - Name : Sonar-Scanner-4.7
  - Select Sonar Version
  - Save it
- Create a jenkins pipeline
```
  pipeline { 
    agent any  
    stages { 
        stage('Build') { 
            steps { 
                // compile code  
	// if successful, move build artifacts to the desired location 
            } 
        } 
        stage('Test') {  
            steps { 
                // check if artifacts are present in the correct location 
	// load test data into the database 
	// execute the test case 
	// continue only if tests passed 
            } 
        }uio 
        stage('Deploy') {  
            steps { 
                // Fetch tested code and deploy it to production 
            } 
        } 
    } 
} 
```
### What is Jenkinsfile?
- Jenkinsfile is nothing but a simple text file which is used to write the jenkins pipeline and to automate the continuos integration process.
- Jenkinsfile usually checked in along with the project source code in Git repo. Ideally every application will have its own Jenkinsfile.

### Jenkins file can be written in two ways
- Scripted pipeline syntax
- Declarative pipeline syntax
### What is Jenkins scripted pipeline?
- Jenkins piepline are traditionally written as scripted pipelines. Ideally the scripted pipeline is stored in Jenkins webUI jenkins file. The end to end scripted is written in Groovy.
