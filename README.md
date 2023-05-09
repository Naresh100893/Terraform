# Terraform
## Tearraform (HashiCorp) , An End-to-End IaC preparation.

**Introduction to Terraform Workflow using Terraform Commands:**

**Init**: This is used to initialise a wokrimng directory containing terrform config files.

**Validate**: Validate the Terraform configuration files in that respective directory to ensure they are syntactically valid and internally consistent. 

**Plan**: Creates an execution plan , Terraform performs a refresh and determines what actions are necessary to achieve the desired state specified in configuration files.

**Apply**: Used to apply the changes required to reach the desired state of the configuration. By default, apply scans the current directory for the configuration and applies the changes appropriately.

**Destroy**: Used to destroy the terraform-managed infrastucture, This will ask for confirmation before destroying.

Terraform Command Basics: 

Step-01: Introduction

-> Understand basic Terraform commands;
Terraform Init
Terraform Validate
Terraform plan
Terraform apply
Terraform destroy

Step-02: Review Terraform manifest for EC2 Instance
Pre- conditions-1: Ensure you have default-vpc in that respective region
Pre-Condition-2: Ensure ANI you are provisioning exists in that region if not update AMI ID
Pre-Condition-3: Verify your AWS credentials in$HOME/.aws/credentials

# Terraform Settings Block
terraform {
  required_providers {
    aws = {
      source  = "hashicorp/aws"
      #version = "~> 3.21" # Optional but recommended in production
    }
  }
}
 
# Provider Block
provider "aws" {
  profile = "default" # AWS Credentials Profile configured on your local desktop terminal  $HOME/.aws/credentials
  region  = "us-east-1"
}

# Resource Block
resource "aws_instance" "ec2demo" {
  ami           = "ami-04d29b6f966df1537" # Amazon Linux in us-east-1, update as per your region
  instance_type = "t2.micro"
}


Step-03: Terraform Core Commands

# Initialize Terraform
terraform init

# Terraform Validate
terraform validate

# Terraform Plan to Verify what it is going to create / update / destroy
terraform plan

# Terraform Apply to Create EC2 Instance
terraform apply 

Step-04: Verify the EC2 Isnatnce in AWS Management Console
goto AWS management console --> Services --> EC2
Verify newly created EC2 Instance

Step-05: Destroy Infrastucture
# Destroy EC2 Instance
terraform destroy

# Delete Terraform files 
rm -rf .terraform*
rm -rf terraform.tfstate*

Step-08: Conclusion
*Re-iterate what have we learned in this scetion
Learned about Important Teraform commands.



