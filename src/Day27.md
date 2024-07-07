### Two seperate files (provider & main)
- provider.tf
```
provider "aws"{
    region = "ap-south-1"
    access_key = "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9"
    secret_key = "eyJhbHbjsakGhmBcjblJBLiIsInR5cCI6IkpXVCJ9iwrFJHrdf"
}
```
- main.tf
```
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
- Run the below commands :
- $ terrafrom init
- $ terraform fmt
- $ terrafrom validate
- $ terrafrom plan
- $ terrafrom apply
- After executing terrafrom apply it creates a terrafrom.tfstate file in the same directory.

![image](https://github.com/Abhinavcode13/DevOpsDrift-Daily/assets/126642111/b4e1818d-6682-4411-8775-36bb18c5e901)

## Variables in HCL 
- We can maintain a seperate file for variables.
- $ vi var.tf
```
variable "ami"{
  description = "Amazon machine image value"
  default = "ami-05c8cca4485f8b138a"
}
variable "instance_type"{
  description = "Amazon Instance Type"
  default = "t2.micro"
}
variable "instances_count"{
  description = "Total number of instances"
  default = "3"
}
```
- Create main tf file using variables
- $ vi main.tf
```
provider "aws"{
    region = "ap-south-1"
    access_key = "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9"
    secret_key = "eyJhbHbjsakGhmBcjblJBLiIsInR5cCI6IkpXVCJ9iwrFJHrdf"
}
resource "aws_instance" "AWSServer"{
    count = "${var.instances_count}"
    ami = "${var.ami}"
    instance_type = "${var.instance_type}"
    key_name = "linux"
    security_groups = ["launch-wizard-1"]
    tags = {
        Name = "Terraform server - ${count.index}"
    }
}
```
## Comments in terrafrom script
- `#` for single line comment
- `//` also for single line comment
- `/* & */` for multi line comments

## Host static website using Terraform
- Make a new folder : $ mkdir test
- $ cd test
- $ vi installHttpd.sh
- Paste the shell file content in installHttpd.sh
```
#!/bin/bash
sudo su
yum install httpd -y
ccd /var/www/html
echo "<html><h1>Welcome to devops-drift repo!!</h1></html>" indeex.html
service httpd start
```
-  $ chmod u+x installHtppd.sh - change user permission
-  $ vi main.tf
```
provider "aws"{
    region = "ap-south-1"
    access_key = "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9"
    secret_key = "eyJhbHbjsakGhmBcjblJBLiIsInR5cCI6IkpXVCJ9iwrFJHrdf"
}
resource "aws_instance" "AWSServer"{
#   count = "${var.instances_count}"
    ami = "${var.ami}"
    instance_type = "${var.instance_type}"
    key_name = "linux"
    security_groups = ["launch-wizard-1"]
    user_data = "${file("installHtppd.sh")}"  
    tags = {
        Name = "Terraform server - ${count.index}"
    }
}
```
- Run the following commands :
- $ terrafrom init
- $ terraform fmt
- $ terrafrom validate
- $ terrafrom plan
- $ terrafrom apply
