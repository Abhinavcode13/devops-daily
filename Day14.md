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
### Setting up the DEV server
- Create a job in jenkins -> new item(abhinav-dev-job) -> freestyle project -> click on OK
- Source code management section -> Git -> Repo URL -> Credentials
- Build triggers -> Poll SCM -> Schedule (*****)
- Build environment -> Delete workspace before build starts
- Build -> Invoke top level maven targets -> maven 3.6 version -> goals (clean package)
- Post build actions -> select deploy war to container -> location (**/*.war) -> Credentials -> Tomcat URL of dev server -> click on APPLY and save
### Setting up the SIT server
- Create jenkins build pipeline to execute jobs in sequence.
- Create a job in jenkins -> new item(abhinav-sit-job) -> freestyle project -> click on OK
- Source code management section -> Git -> Repo URL -> Credentials
- Build triggers -> Build after other projects are built -> project to watch (abhinav-dev-job)
- Build environment -> Delete workspace before build starts
- Build -> Invoke top level maven targets -> maven 3.6 version -> goals (clean package)
- Post build actions -> select deploy war to container -> location (**/*.war) -> Credentials -> Tomcat URL of sit server -> click on APPLY and save
### Setting up the UAT server
- Create jenkins build pipeline to execute jobs in sequence.
- Create a job in jenkins -> new item(abhinav-uat-job) -> freestyle project -> click on OK
- Source code management section -> Git -> Repo URL -> Credentials
- Build triggers -> Build after other projects are built -> project to watch (abhinav-sit-job)
- Build environment -> Delete workspace before build starts
- Build -> Invoke top level maven targets -> maven 3.6 version -> goals (clean package)
- Post build actions -> select deploy war to container -> location (**/*.war) -> Credentials -> Tomcat URL of UAT server -> click on APPLY and save
### View Build-pipeline
- View Build-pipeline (+) icon -> new view (add a name) -> Type (build pipeline view) -> Build pipeline view title (dark-pipeline) -> Upstream/downstream config (select the initial job -> dev job)
- CLick on apply and save it
