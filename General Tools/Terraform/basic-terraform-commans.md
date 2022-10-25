# Basic Terraform Commands


- `terraform init` - Initialize Terraform directory. Should be run when you first setup a new Terraform file or pull a new Terraform directory. This will download and install the needed providers.

- `terraform fmt` - Automatically formats your Terraform files.

- `terraform validate` - Looks at file and verifies that syntax is correct and verifies that the set up is internally consistent. 

- `terraform plan` - Checks current state and compares it to any change in the Terraform configuration and prints out the proposed changes. Allows you to view changes before applying them.

- `terraform apply` - Applies the configuration. Shows you the proposed changes and asks you to verify that those changes are what you want.

- `terraform show` - Shows you the output of the `terraform.tfstate` file. The state is how Terraform keeps track of what it is managing.

- `terraform state list` - Lists all the resources in the Terraform state.

- `terraform destroy` - Terminates the resources that Terraform is managing in it's state.

#GeneralTools
	#Terraform