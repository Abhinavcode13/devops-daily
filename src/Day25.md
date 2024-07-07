![image](https://github.com/Abhinavcode13/DevOpsDrift-Daily/assets/126642111/82a8fe9e-b0bc-4fd0-9ce9-281ef34b96fe)


## Terraform
- Terraform is an infrastructure as code tool that enables you to safely and predictably provision and manage infrastructure in any cloud.

### Benefits of using Terraform
- Does orchestration, not just configuration management
- Supports multiple providers such as AWS, Azure, Oracle, GCP, and many more
- Provide immutable infrastructure where configuration changes smoothly
- Uses easy to understand language, HCL (HashiCorp configuration language)
- Easily portable to any other provider

### Install Terraform
- git clone https://github.com/hashicorp/terraform.git
- cd terraform
- go install
- Verify the installation - terraform -help

### HCL
- Blocks in HCL
- Syntax:
```
block_type {
attribute1=value1
attribute2=value2
}
```
- Example
```
resource "aws_instance" "example" {
  instance_type = "t2.micro"
  ami           = "ami-abc123"
}
```
### Datatypes in HCL
- String
```
variable "name" {
  type    = string
  default = "John Doe"
}
```
- Number
```
variable "age" {
  type    = number
  default = 25
}
```
- Bool
```
variable "is_enabled" {
  type    = bool
  default = true
}
```
- list
```
variable "fruits" {
  type    = list(string)
  default = ["apple", "orange", "banana"]
}
```
- Map
```
variable "user" {
  type = map(string)
  default = {
    name  = "Alice"
    age   = "30"
    email = "alice@example.com"
  }
}
```
- Set
```
variable "tags" {
  type    = set(string)
  default = ["dev", "prod", "test"]
}
```
