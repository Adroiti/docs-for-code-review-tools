Pattern: Use of automatic default network creation for Google IAM

Issue: -

## Description

The default network which is provided for a project contains multiple insecure firewall rules which allow ingress to the project's infrastructure. Creation of this network should therefore be disabled.

**Resolution**: Disable automatic default network creation.

## Examples

The following example will fail the google-iam-no-default-network check.

```terraform
 resource "google_project" "bad_example" {
   name       = "My Project"
   project_id = "your-project-id"
   org_id     = "1234567"
   auto_create_network = true
 }
 
```

The following example will pass the google-iam-no-default-network check.

```terraform
 resource "google_project" "good_example" {
   name       = "My Project"
   project_id = "your-project-id"
   org_id     = "1234567"
   auto_create_network = false
 }
```

## Further reading

- [https://registry.terraform.io/providers/hashicorp/google/latest/docs/resources/google_project#auto_create_network](https://registry.terraform.io/providers/hashicorp/google/latest/docs/resources/google_project#auto_create_network)