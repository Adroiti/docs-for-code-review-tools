Pattern: Users granted service account access at the organization level

Issue: -

## Description

Users with service account access at organization level can impersonate any service account. Instead, they should be given access to particular service accounts as required.

**Resolution**: Provide access at the service-level instead of organization-level, if required.

## Examples

Example of **incorrect** code:

```terraform

```

Example of **correct** code:

```terraform
resource "google_organization_iam_binding" "organization-123" {
	org_id  = "org-123"
	role    = "roles/nothingInParticular"
}
```