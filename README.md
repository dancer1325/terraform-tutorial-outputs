# Learn Terraform outputs

This repo is a companion repo to the [Learn Terraform outputs](https://developer.hashicorp.com/terraform/tutorials/configuration-language/outputs) tutorial.

## Goal
* Deploy infrastructure on AWS
* Create output values
  * to export structured data about your resources
  * formatted to .json

## Prerequisites
* Terraform [v1.2+](https://developer.hashicorp.com/terraform/tutorials/aws-get-started/install-cli) installed locally
* AWS account with [associated credentials](https://registry.terraform.io/providers/hashicorp/aws/latest/docs#authentication-and-configuration)
  * via
    * add in the 'provider' block
    * environment variables
      * 'AWS_ACCESS_KEY_ID'
      * 'AWS_SECRET_ACCESS_KEY'
      * 'AWS_REGION'
    * credential files
      * `aws config` & pass the 'AWS_ACCESS_KEY_ID' & 'AWS_SECRET_ACCESS_KEY'

## How to run?
* `terraform init`
* `terraform apply`
* `terraform output`
  * query the outputs
  * `terraform output lb_url`
    * get specific output
  * `terraform output -raw lb_url`
    * get the output for machine-readable format
  * `terraform output -json`
    * get the outputs in .json format
* `curl $(terraform output -raw lb_url)`
  * confirm that you can access to ELB
* terraform destroy
  * clean up the infrastructure