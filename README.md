## Cortex Terraform Cloud Example

Example that shows an example of using a Cortex workflow to create a new Terraform workspace in an existing repository.

![workflow](/images/workflow.png)

### Cookiecutter Template

This repo contains a CookieCutter template based on the tfc guide example from Hashicorp.

### Workflow Yaml

It also contains a workflow yaml - this workflow uses the included cookiecutter template to append to an existing infra repo under the path `modules/ec2s` and then creates the workspace in Terraform Cloud.

## Prerequisites:
* Terraform Cloud Account (you can sign up for a free one!)
* Cortex instance
* GitHub organization (you can create your own for free!)


#Terraform Files

As stated above this is based on Hashicorps [TFC Guide Example](https://github.com/hashicorp/tfc-guide-example) repo and we have modified some of the value fields with cookiecutter place holders. For example, in the original `main.tf` on line 5 we have:

 <code> region = var.region </code>

In this repo, that line now reads:

<code>  region = "{{ cookiecutter.region }}" </code>

The value will be driven by the `region` field in the cookiecutter template (`cookiecutter.json`).


  
