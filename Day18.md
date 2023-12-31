## Writing Jenkins Pipeline
```
pipeline { 
    agent any 
    environment { 
        PATH="Maven-path"
    } 
    stages { 
        stage('GetCode') { 
          steps {  
                git 'Git-url'  
            } 
      } 
        stage('Build'){ 
            steps { 
                sh 'mvn clean package'  
            } 
        } 
        stage('Sonar analysis') { 
            steps { 
                withSonarQubeEnv('Sonar-Server-7.8'){
                    sh "mvn sonar:sonar"
            } 
        } 
    } 
}
```
