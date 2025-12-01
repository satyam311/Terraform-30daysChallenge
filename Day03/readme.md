# Day 03 - S3 Bucket 

### Pre-requisite 

AWS CLI must be installed on your system.
doc : https://docs.aws.amazon.com/cli/latest/userguide/getting-started-install.html

In the terminal : 
type "aws configure" and provide the security credentials like key and secrets of aws account.


**Documentation** : https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/s3_bucket

```
terraform {
  required_providers {
    aws = {
      source  = "hashicorp/aws"
      version = "~> 6.0"
    }
  }
}

# Configure the AWS Provider
provider "aws" {
  region = "us-east-1"
}
#create s3 bucket

resource "aws_s3_bucket" "first_bucket" {
  bucket = "satyam-987321-tf-test-bucket"

  tags = {
    Name        = "My bucket"
    Environment = "Dev"
  } 
}
```

**What terraform init Does ?**

1. Downloads and installs required providers
2. Initializes the backend
3. Sets up working directory
4. Validates version compatibility

In Short, It install all dependencies and set up the environment before running anything.


**What terraform plan Does?**

1. Reads your configuration -> Terraform looks at your .tf files (like the S3 bucket you created).
2. Reads the current state -> From terraform.tfstate (local) or a remote backend (S3, Terraform Cloud, etc.)
3. Compares desired state vs current state -> 
4. Shows the exact actions it will perform -> It tells you:What will be created and What will be updated and What will be destroyed.

In short : "terraform plan does not make any changes.
It only displays the changes so you can review them before applying."


**What terraform apply Does?**

1. Re-runs the plan
2. Shows the execution plan
3. Asks for confirmation
4. Applies the changes
5. Updates the state file


**What terraform destroy Does?**

1. Reads your Terraform state
2. Calculates what needs to be destroyed
3. Shows a destroy plan
4. Asks for confirmation
5. Deletes the resources
6. Updates the state file
 

**Other commands :**

```
Terraform Command	Purpose / Feature
terraform init	Initializes directory, downloads providers, sets up backend
terraform plan	Shows execution plan and previews changes (add/update/destroy)
terraform apply	Applies the changes to create/update/destroy resources
terraform destroy	Deletes all resources managed by Terraform
terraform validate	Validates Terraform configuration syntax & internal consistency
terraform fmt	Automatically formats .tf files to standard style
terraform show	Shows the state or plan details in a readable format
terraform state	Manages Terraform state: list, move, remove, and inspect resources
terraform output	Displays the values of output variables defined in configuration
terraform refresh (deprecated)	Refreshes state with real-world cloud values; replaced by apply -refresh-only
terraform import	Imports existing cloud resources into Terraform state
terraform graph	Generates a dependency graph of infrastructure resources
terraform login	Authenticates with Terraform Cloud / Enterprise
terraform providers	Lists providers used and their versions
terraform version	Shows the installed Terraform CLI version
terraform workspace	Manages multiple environments (dev/stg/prod) using workspaces
terraform taint (deprecated)	Marks a resource to be recreated; replaced by apply -replace
terraform apply -replace=resource	Re-creates a specific resource (modern replacement for taint)
```

**how to use auto approve with terraform command:**

terraform appky --auto-approve



