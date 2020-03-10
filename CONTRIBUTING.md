# Contributing to this module


This repo provides a template for creating a new Terraform module, following
the [standard module structure](https://www.terraform.io/docs/modules/index.html#standard-module-structure) required for publishing to the Terraform
Registry.

## Getting Started

<!-- After creating your copy of the repo, you should replace this section with any 
information specific to development on your module. :)
 -->

This repo has been set up as a Github template repo. You can generate a new
repo from this one using the "Use this template" option above the "Clone or 
download" button.


## Pre-commit hooks

We use [Terraform pre-commit hooks](https://github.com/antonbabenko/pre-commit-terraform)
to ensure consitent formatting and to auto-generate documentation.

### Installation
Make sure you have all [relevant dependencies](https://github.com/antonbabenko/pre-commit-terraform/blob/master/README.md#1-install-dependencies) installed.

Run `pre-commit install` at the root of your repo.

### Usage

If you prefer to generate your own docs, keep the following line commented out
in `.pre-commit.yaml`:  `- id: terraform_docs`. Keep in mind, however, that if
you choose to publish your module to the Terraform Registry, docs will be auto-
generated, so you may want to keep that hook in place to see how it behaves 
before you publish.

If you want to use the terraform_docs pre-commit hook, uncomment the above line.

This hook will delete and replace anything in your `README.md` between the 
following lines:

```
<!-- BEGINNING OF PRE-COMMIT-TERRAFORM DOCS HOOK -->
<!-- END OF PRE-COMMIT-TERRAFORM DOCS HOOK -->
```
