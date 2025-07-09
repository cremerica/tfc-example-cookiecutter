## Cortex Terraform Cloud Example

Example that shows an example of using a Cortex workflow to create a new Terraform workspace in an existing repository.

### Cookiecutter Template

This repo contains a CookieCutter template based on the tfc guide example from Hashicorp.

### Workflow Yaml

It also contains a workflow yaml - this workflow uses the included cookiecutter template to append to an existing infra repo under the path `modules/ec2s` and then creates the workspace in Terraform Cloud.

## Prerequisites:
* Terraform Cloud Account (you can sign up for a free one!)
* Cortex instance
* GitHub organization (you can create your own for free!)

  
