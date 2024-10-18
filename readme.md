# Learning Terraform
I'm branching out! This is a repo where I document my learnings around using Terraform and other infrastructure concepts. Currently following [this tutorial](https://developer.hashicorp.com/terraform/tutorials/docker-get-started/install-cli) from HashiCorp's website.

Also currently starting their [AWS tutorial](https://developer.hashicorp.com/terraform/tutorials/aws-get-started)

## Helpful Commands
* `terraform init` starts up a terraform project and creates the first `main.tf` file that controls the orchestration.
* `main.tf` is where the configuration for your project goes. It is where you define the provider (`docker`, `aws`, or other cloud providers), and the instance that you're setting up.
* `terraform apply` takes the `main.tf` file and provisions resources based on the configuration in `main.tf`
* `terraform destroy` unmakes all instances that were created using this `main.tf` file
* `terraform show list` shows all existing (and running) provisions created by this `main.tf` file
* `.terraform.lock.hcl` is a file that is created whenever `terraform init` is run, and is a dependency file that acts kind of like a `package-lock.json` would for a Node/JavaScript project
* Since Terraform loads all `.tf` files at `apply` time, creating a file like `variables.tf` allows you to be more flexible with what you call your stuff, and `outputs.tf` makes it easier to debug by surfacing values in the terminal.
* You can manage your workspaces remotely using HCP Terraform (the cloud platform that can host your configs and your environment variables)