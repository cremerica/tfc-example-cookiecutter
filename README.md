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


##Terraform Files

As stated above this is based on Hashicorps [TFC Guide Example](https://github.com/hashicorp/tfc-guide-example) repo and we have modified some of the value fields with cookiecutter place holders. For example, in the original `main.tf` on line 5 we have:

 <code> region = var.region </code>

In this repo, that line now reads:


<code>  region = "{{ cookiecutter.region }}" </code>

The value will be driven by the `region` field in the cookiecutter template (`cookiecutter.json`).

## Getting Started

First, make sure you meet the prerequesites above. 

### Setting Secrets

Next, let's set up secrets in Cortex. To do this, log into Cortex and go to Settings > Authentication and Access > Secrets. Create the following secrets (note - you can use different names, just make sure you also edit their reference in the workflow ):

* **tf_token:** A [User API](https://developer.hashicorp.com/terraform/cloud-docs/users-teams-organizations/api-tokens#user-api-tokens) token from Terraform Cloud.
* **tf_organization:** The organization name in Terraform Cloud
* **aws_access_key_id:** Your AWS Access Key ID - this is set as environment variablels in the Terraform Workspace in order to deploy to EC2 instance to AWS.
* **aws_secret_access_key:** Your AWS Secret Access Key - this is set as environment variablels in the Terraform Workspace in order to deploy to EC2 instance to AWS.

### Register Scaffolder

Fork this repository to an organization in Git that Cortex has access to. Then follow our [docs](https://docs.cortex.io/workflows/scaffolder) to register the scaffolder template.

**Note:** This scaffolder template assumes you have a `modules/ec2s` folder structure in the repo where the workspace is created. If you have a different path, modify the path in the template.

### Create the workflow

To use the Yaml in this repository you have two options:
1. Use (this)[https://docs.cortex.io/api/rest/workflows#post-api-v1-workflows] API endpoint to add it.
2. Use (GitOps)[https://docs.cortex.io/workflows/create/workflows-as-code] to add it

You can also use the UI and use the YAML file as a guide.


  
