# Task 
**Create a terraform file to provision VPC and S3 bucket and create implicit dependency between them, don't worry about the variables, files etc.**

```
terraform {
  required_providers {
    aws = {
      source = "hashicorp/aws"
      version = "6.23.0"
    }
  }
}

provider "aws" {
  region = "us-east-1"
}
# --------------------------
# Create a VPC
# --------------------------
resource "aws_vpc" "my_vpc" {
  cidr_block       = "10.0.0.0/16"
  instance_tenancy = "default"

  tags = {
    Name = "main"
  }
}
# --------------------------
# Create an S3 Bucket
# Implicit dependency: uses VPC ID inside tags
# --------------------------
resource "aws_s3_bucket" "my-s3" {
  bucket = "my-tf-test-bucket-sattu-987321"

  tags = {
    Name        = "My bucket"
    Environment = "Dev"
    VPC_ID = aws_vpc.my_vpc.id
  }
}
```
