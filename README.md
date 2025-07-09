This repo contains a CookieCutter template based on the tfc guide example from Hashicorp.

It also contains a workflow yaml - this workflow uses the included cookiecutter template to append to an existing infra repo under the path `modules/ec2s`. It then uses the Terraform Cloud API to create a new workspace, adding two environment variables 
