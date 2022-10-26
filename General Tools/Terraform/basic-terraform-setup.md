# Basic Terraform Setup

---
## Docs and Source
[Docs](https://learn.hashicorp.com/tutorials/terraform/aws-build?in=terraform/aws-get-started)

---
## Explanation and Notes

The setup is fairly simple process.

1. Create a `main.tf` file for everything we need.
2. Fill out the config file like the code example below.
3. Run `terraform init` to download the providers and setup the directory.
4. Run `terraform fmt` so that Terraform formats the file to make it all pretty.
5. Run `terraform validate` to confirm that the file has the right syntax and is formatted correctly
6. Run `terraform plan` to have Terraform look through the file and give you a print out of what the configuration you wrote will do.
7. Run `terraform apply` to apply the plan. Type in `yes` when you've confirmed that Terraform will do what you want it to.
8. Once you get the OK from Terraform, you can type in `terraform show` to see the state of Terraform. Which shows what is recorded in the Terraform state file. Which is what Terraform uses to keep track of what is set up.
9. You can see a more detailed view of each of the deployed resources using `terraform state list`.

---
## Code Example

```Terraform
terraform {
  required_providers {
    aws = {
      source  = "hashicorp/aws"
      version = "~> 4.16"
    }
  }

  required_version = ">= 1.2.0"
}

provider "aws" {
  region  = "us-west-2"
}

resource "aws_instance" "app_server" {
  ami           = "ami-830c94e3"
  instance_type = "t2.micro"

  tags = {
    Name = "ExampleAppServerInstance"
  }
}

```


#GeneralTools 
	#Terraform 