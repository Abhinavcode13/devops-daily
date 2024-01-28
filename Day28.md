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
