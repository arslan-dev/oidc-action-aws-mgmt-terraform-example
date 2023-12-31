# AWS EC2 Instance Management GitHub Action

This project provides a GitHub Action and Terraform configuration example that allows you to start and stop an AWS EC2 instance manually from GitHub UI using OIDC to connect GitHub to AWS.

Terraform configuration will set up five resources:

1. an EC2 instance
2. an OIDC provider
3. a role with trust
4. a permission to only start and stop newly created EC2 instance (and only it)
5. a role-to-permission attachment.

Then, "EC2 Instance Management" Action will provide you with the ability to start and stop this EC2 instance from the GitHub UI.

## Usage

1. Fork the repository and clone the forked one
2. Go to the repo's folder, run `terraform init && terraform apply` command and provide necessary values.
3. Using terraform output, fill out these GitHub Secrets (Repository Settings -> Secrets and variables):

- AWS_ROLE_TO_ASSUME
- AWS_REGION
- AWS_INSTANCE_ID

4. In the repository page on GitHub click on the "Actions" tab in the top navigation bar
5. In the left sidebar, click "EC2 Instance Management" workflow.
6. At the top of the workflow page, you'll see a "Run workflow" dropdown button. Click on it.
7. Terraform runs EC2 Instance, so in order for it to be stopped, select "Stop" action and press "Run workflow" button.
