## Creating S3 bucket using Terraform
- HCL script used to create S3 bucket is given below :
```
provider "aws" {
  region     = "ap-south-1"
  access_key = "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9"
  secret_key = "eyJhbHbjsakGhmBcjblJBLiIsInR5cCI6IkpXVCJ9iwrFJHrdf"
}

resource "aws_s3_bucket" "S3bucketabhinavkumar" {
  bucket = "s3bucketabhinavkumar"
  acl    = "private"

  versioning {
    enabled = true
  }

  tags = {
    Name = "S3 bucket by abhinav"
  }
}
```
## To create VPC resources on AWS
```
module "vpc" {
  source = "terraform-aws-modules/vpc/aws"

  name = "my-vpc"
  cidr = "10.0.0.0/16"

  azs             = ["eu-west-1a", "eu-west-1b", "eu-west-1c"]
  private_subnets = ["10.0.1.0/24", "10.0.2.0/24", "10.0.3.0/24"]
  public_subnets  = ["10.0.101.0/24", "10.0.102.0/24", "10.0.103.0/24"]

  enable_nat_gateway = true
  enable_vpn_gateway = true

  tags = {
    Terraform = "true"
    Environment = "dev"
  }
}
```
## Provides a CloudWatch Composite Alarm resource.
```
resource "aws_cloudwatch_composite_alarm" "example" {
  alarm_description = "This is a composite alarm!"
  alarm_name        = "example-composite-alarm"

  alarm_actions = aws_sns_topic.example.arn
  ok_actions    = aws_sns_topic.example.arn

  alarm_rule = <<EOF
ALARM(${aws_cloudwatch_metric_alarm.alpha.alarm_name}) OR
ALARM(${aws_cloudwatch_metric_alarm.bravo.alarm_name})
EOF

  actions_suppressor {
    alarm            = "suppressor-alarm"
    extension_period = 10
    wait_period      = 20
  }
}
```
- For more reference to write any script in HCL language : https://registry.terraform.io/providers/hashicorp/aws/latest/docs 
- End of Terraform 
