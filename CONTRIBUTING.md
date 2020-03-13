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

## Version tags

We're using a github action to automatically create tags and bump the version
on merge to master.

We have already installed this action here, but disabled; you can opt in to
using it following the [instructions below]().

For full usage instructions, consult the [official documentation](https://github.com/marketplace/actions/github-tag-bump#usage)


## Setting up the github action

<!-- TODO: Test what happens with the action if no tag is present. Add a note
  to manually create the first tag if needed.-->

All pre-release versions should be lower than `v1.0.0`

<!-- Rename `github/workflows/bump_tag.yml` to  `.github/workflows/bump_tag.yml` so
Github will recognize the action.

Or just comment out the contents of the yaml?
 -->

<!-- Looks like this happens automatically. Test/ verify
 -->
<!-- Set a `GITHUB_TOKEN` Github secret in your repo (this is necessary for the action to work).
 -->

Set any [optional environment variables](https://github.com/marketplace/actions/github-tag-bump#options)

TODO: Set recommendations for the optional env var, if different from defaults?
```
Environment Variables

DEFAULT_BUMP (optional) - Which type of bump to use when none explicitly provided (default: minor).
WITH_V (optional) - Tag version with v character.
RELEASE_BRANCHES (optional) - Comma separated list of branches (bash reg exp accepted) that will generate the release tags. Other branches and pull-requests generate versions postfixed with the commit hash and do not generate any tag. Examples: master or .* or release.*,hotfix.*,master ...
CUSTOM_TAG (optional) - Set a custom tag, useful when generating tag based on f.ex FROM image in a docker image. Setting this tag will invalidate any other settings set!
SOURCE (optional) - Operate on a relative path under $GITHUB_WORKSPACE.
DRY_RUN (optional) - Determine the next version without tagging the branch. The workflow can use the outputs new_tag and tag in subsequent steps. Possible values are true and false (default).
```
