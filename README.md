# Terraform
## Tearraform (HashiCorp) , An End-to-End IaC preparation.

**Introduction to Terraform Workflow using Terraform Commands:**

**Init**: This is used to initialise a wokrimng directory containing terrform config files.

**Validate**: Validate the Terraform configuration files in that respective directory to ensure they are syntactically valid and internally consistent. 

**Plan**: Creates an execution plan , Terraform performs a refresh and determines what actions are necessary to achieve the desired state specified in configuration files.

**Apply**: Used to apply the changes required to reach the desired state of the configuration. By default, apply scans the current directory for the configuration and applies the changes appropriately.

**Destroy**: Used to destroy the terraform-managed infrastucture, This will ask for confirmation before destroying.

