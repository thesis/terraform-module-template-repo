
# Module Name (Required)

Module description

## Compatibility (Optional)


## Usage (Required)

Sample module block showing required fields configured.  You can have
multiple examples if it makes sense for the module.

```hcl
module "your_custom_name_for_your_instance_of_this_module" {
  source                = "git@github.com:thesis/this-module-name.git"
  name                  = "name-of-your-project"
  org_id                = "your-org-id"
  billing_account       = "your-billing-account"
  project_owner_members = ["john@email.co", "lilly@email.co",]
  location              = "us-central1"
}
```

## Inputs (Required)

Table of available module inputs in the format:

|Name | Description | Type |Default | Required
--- | --- | --- | --- | --- |
`inputName`| Description of this input | input type | `default value` | boolean


## Notes (Optional)

Anything quirky about the module folks may want to know about. Relevant
links or additional useful information.  Format is up to you.

## License (Required)

If open-sourced, list license. Else:

Copyright Thesis, Inc., 2020
