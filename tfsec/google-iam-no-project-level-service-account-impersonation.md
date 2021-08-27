Pattern: Users granted service account access at the project level

Issue: -

## Description

Users with service account access at project level can impersonate any service account. Instead, they should be given access to particular service accounts as required.

**Resolution**: Provide access at the service-level instead of project-level, if required.

## Examples

Example of **incorrect** code:

```terraform

```

Example of **correct** code:

```terraform
resource "google_project_iam_binding" "project-123" {
	project = "project-123"
	role    = "roles/nothingInParticular"
}
```