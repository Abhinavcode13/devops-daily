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

- Terraform architecture mainly consists of the following components:

1) Terraform Core
2) Providers
3) State file

- Terrafrom script example (main.tf)
```
provider "aws"{
    region = "ap-south-1"
    access_key = "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9"
    secret_key = "eyJhbHbjsakGhmBcjblJBLiIsInR5cCI6IkpXVCJ9iwrFJHrdf"
}

resource "aws_instance" "AWSServer"{
    ami = "ami-05c8cca4485f8b138a"
    instance_type = "t2.micro"
    key_name = "linux"
    security_groups = ["launch-wizard-1"]
    tags = {
        Name = "REDHAT-EC2-VM1"
    }
}
```
- Create a file main.tf using $ sudo vim main.tf and paste this script in it.
- Excute the above mentioned terrafrom commands.
