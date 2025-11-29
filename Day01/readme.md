# Introduction to Terraform

### What is Infrastructure as Code?
Provisioning your infrastructure through code instead of manual processes.

### Why Infrastructure as Code?

- **Consistency**: Identical environments across dev, staging, and production
- **Time Efficiency**: Automated provisioning saves hours of manual work
- **Cost Management**: Easy to track costs and automate cleanup
- **Scalability**: Deploy to hundreds of servers with same effort as one
- **Version Control**: Track changes in Git
- **Reduced Human Error**: Eliminate manual configuration mistakes
- **Collaboration**: Team can work together on infrastructure

  <img width="861" height="447" alt="Screenshot 2025-11-29 at 1 15 02 PM" src="https://github.com/user-attachments/assets/63620cae-70b3-404e-92e0-1e41f6951ee1" />

### Benefits of IaC
- Consistent environment deployment
- Easy to track and manage costs
- Write once, deploy many (single codebase)
- Time-saving automation
- Reduced human error
- Cost optimization through automation
- Version control for infrastructure changes
- Automated cleanup and scheduled destruction
- Developer focus on application development
- Easy creation of identical production environments for troubleshooting

<img width="834" height="414" alt="Screenshot 2025-11-29 at 1 23 47 PM" src="https://github.com/user-attachments/assets/3d1e6150-8101-43e8-9458-4332be5b892b" />


### What is Terraform?
Terraform is an open-source Infrastructure as Code (IaC) tool created by HashiCorp that lets you provision, manage, and automate cloud infrastructure using code.

### How Terraform Works
Write Terraform files → Run Terraform commands → Call AWS APIs through Terraform Provider

**Terraform Workflow Phases:**
1. `terraform init` - Initialize the working directory
2. `terraform validate` - Validate the configuration files
3. `terraform plan` - Create an execution plan
4. `terraform apply` - Apply the changes to reach desired state
5. `terraform destroy` - Destroy the infrastructure when needed

### Installation of Terraform 

on mac : 

https://developer.hashicorp.com/terraform/install

```
brew tap hashicorp/tap
brew install hashicorp/tap/terraform
```

in case of error realted to xcode : 

Install Command Line Tools:

```xcode-select --install```

### Useful Commands

```
terraform -install-autocomplete
alias tf=terraform
terraform -version
```

