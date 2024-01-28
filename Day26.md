## Install Terraform in AWS
- Create 1 ec2 instance initally and IAM user group.
- Below are the commands to install terraform in RedHat operating system
- $ sudo yum install -y yum-utils
- $ sudo yum-config-manager --add-repo https://rpm.releases.hashicorp.com/RHEL/hashicorp.repo
- $ sudo yum -y install terraform
- $ terraform -version
## Terraform commands
- Initailize terraform : $ terrafrom init
- Format the script : $ terraform fmt
- Validate the script : $ terrafrom validate
- Create execution plan for script : $ terrafrom plan
- Create infrastructure by running script : $ terraform -auto-approve
## Terraform Architecture

![image](https://github.com/Abhinavcode13/DevOpsDrift-Daily/assets/126642111/74a58011-51c4-4478-90d4-b2a1b7813eee)

