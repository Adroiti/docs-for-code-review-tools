Pattern: Default network created at project level

Issue: -

## Description

The default network which is provided for a project contains multiple insecure firewall rules which allow ingress to the project's infrastructure. Creation of this network should therefore be disabled.

**Resolution**: Disable automatic default network creation.

## Examples

Example of **incorrect** code:

```terraform
resource "google_project" "bad_example" {
  name       = "My Project"
  project_id = "your-project-id"
  org_id     = "1234567"
  auto_create_network = true
}
```

Example of **correct** code:

```terraform
resource "google_project" "good_example" {
  name       = "My Project"
  project_id = "your-project-id"
  org_id     = "1234567"
  auto_create_network = false
}
```