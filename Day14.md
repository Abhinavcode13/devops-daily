## Jenkins Pipeline
- Sequence of jobs execution is called of pipeline
- For our application we will have multiple environment like DEV,SIT,UAT,PILOT and PROD
### Steps to create Jenkins pipeline
- Create ec2 vm and install tomcat server (DEV)
- Create ec2 vm and install tomcat server (SIT)
- Create ec2 vm and install tomcat server (UAT)
- Create ec2 vm and instal Jenkins
- Install jdk, maven, Git, deploy to container in jenkins server VM
- Create Jobs in jenkins server
  - DEV-job -> Dev server
  - SIT-job -> Sit server (SIT job should execute if DEV job is stable)
  - UAT-job -> Uat server (UAT job should execute if SIT job is stable)
- Create jenkins build pipeline to execute jobs in sequence.
